<template>
  <v-app>
    <v-container class="accent">
      <h1>Formulario y tabla con Vuetify y VeeValidate</h1>
      <formu-datos />
    </v-container>
  </v-app>
  <!-- <div id="app">
      <formu-datos />
  </div> -->
</template>

<script>
import FormuDatos from './components/FormuDatos.vue'
export default {
  name: 'App',
  components: {
    FormuDatos
  }
}
</script>

