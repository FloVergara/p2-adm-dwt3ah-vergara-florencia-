<template>
  <div class="about pa-8">
    <v-carousel>
      <v-carousel-item
        v-for="(item,i) in items"
        :key="i"
        :src="item.src"
      ></v-carousel-item>
    </v-carousel>

        <v-row class="text-center">
        <v-col cols="12">
            <v-img :src="require('../assets/logoNota.svg')" class="my-3" contain height="150"/>
        </v-col>
        <v-col class="mb-4">
            <h1 class="display-2 font-weight-bold mb-3">BENEFICIOS DE UTILIZAR UNA LISTA DE TAREAS PARA GESTIONAR TU TIEMPO</h1>
        </v-col>        
        </v-row>
        <v-row class="text-center">
        <v-col class="mb-4">
            <h2 class="display-5 font-weight-bold mb-3">¿Tienes problemas para <em>gestionar tu tiempo</em> correctamente?</h2>       
        </v-col>
        </v-row>
        <p>Si a menudo te sientes sobrepasado por el montón de cosas pendientes que se van acumulando en tu mente y te pasas el día <strong>deseando tener tiempo para ti </strong>pero cuando llega el momento no sabes exactamente qué hacer…es probable que no dispongas de un sistema que te ayude a administrar tu tiempo correctamente</p>
          <p>Existen gran variedad de técnicas y estrategias que pueden ayudarte y sobre las que encontrarás mucha información fácilmente; pero prácticamente ninguna tan sencilla y tan eficiente como mantener una <em>lista de tareas</em></p>
          <p>Olvidar citas importantes, sentirte desbordado, perder el tiempo en cosas sin importancia…todo esto son síntomas que indican que no estás usando una lista de tareas o que no lo estás haciendo de forma correcta.</p>
          <p>Una lista de tareas es algo que todo el mundo puede usar y no es nada más que un lugar donde anotar todas las ideas o actividades que quieres desarrollar en otro momento, una lista de cosas pendientes</p>
          <p>El concepto de base es muy sencillo: nuestro cerebro no es capaz de almacenar absolutamente todo lo que queremos recordar, así que necesitamos un soporte externo en el que <em>volcar toda esa información</em>, por eso creamos esta App para vos</p>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        items: [
          {
            src: require("../assets/img/1.jpg"),
          },
          {
            src: require("../assets/img/2.jpg"),
          },
        ],
      }
    },
  }
</script>