<template>
    <div class="home">

      <v-text-field
        v-model="nuevaNota"
        @click:append="agregarTarea"
        @keyup.enter="agregarTarea"
        class="pa-3"
        outlined
        label="Nota"
        append-icon="mdi-playlist-plus"
        hide-details
        clearable
      ></v-text-field>

      <v-list
      v-if="tareas.length"
      class="pt-0"
      flat
    >
        <div
        v-for="tarea in tareas"
        :key="tarea.id"
        >
          <v-list-item
            @click="doneTarea(tarea.id)"
            :class="{ 'lime lighten-4' : tarea.done }"
          >
          <template v-slot:default>
            <v-list-item-action>
              <v-checkbox
                :input-value="tarea.done"
                color="lime"
              ></v-checkbox>
            </v-list-item-action>

            <v-list-item-content>
              <v-list-item-title
                :class="{ 'text-decoration-line-through' : tarea.done }"
              >
                {{ tarea.title }}
              </v-list-item-title>
            </v-list-item-content>

            <v-list-item-action>
          <v-btn
          @click.stop="deleteTarea(tarea.id)" 
          icon
          >
            <v-icon color="warning lighten-1">mdi-trash-can-outline</v-icon>
          </v-btn>
        </v-list-item-action>
          </template>
        </v-list-item>
        <v-divider></v-divider>
        </div>
    </v-list>
    <div
    v-else
    class="no-tareas"
    >
    <v-icon
    size="100"
    color="light-green"
    class="no-tasks"
    >
      mdi-check
    </v-icon>
    <div class="text-h5 light-green--text">Sin tareas</div>
    </div>
    </div>
</template>

<script>


  export default {
    name: 'Home',
    data() {
      return {
        nuevaNota: '',
        tareas: []
      }
    },
    methods: {
      agregarTarea() {
        let agregarNota = {
          id: Date.now(),
          title: this.nuevaNota,
          done:false
        }
        this.tareas.push(agregarNota)
        this.nuevaNota = ''
      },
      doneTarea(id) {
        let tarea = this.tareas.filter(tarea => tarea.id === id)[0]
        tarea.done = !tarea.done
      },
      deleteTarea(id) {
        this.tareas = this.tareas.filter(tarea => tarea.id !== id)
      }
    }
  }
</script>

<style lang="sass">
  .no-tareas
    position: absolute
    left: 50%
    top: 50%
    transform: translate(-50%, -50%)
    opacity: 0.5
</style>
