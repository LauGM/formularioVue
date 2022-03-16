<template>
        <v-data-table
        :headers="headers"
        :items="lista"
        item-key="nombre"
        :items-per-page="5"
        class="elevation-1"
        :search="busqueda"
        :custom-filter="filtro"
        >
        <template v-slot:top>
        <v-text-field
          v-model="busqueda"
          label="Buscar"
          class="mx-4"
        ></v-text-field>
      </template>
        </v-data-table>
</template>

<script>
  export default {
    data () {
      return {
        headers: [
          {
            text: 'Nombre',
            align: 'start',
            sortable: true,
            value: 'nombre',
          },
          { text: 'Celular', sortable: false, value: 'celular' },
          { text: 'Email', sortable: false, value: 'email' },
          { text: 'Suscripto', sortable:true, value: 'suscripto' }
        ],
        busqueda:''
        }
        
    },
    props:{
        lista: Array
    },
    methods: {
      filtro (value, busqueda) {
        return value != null &&
          busqueda != null &&
          typeof value === 'string' &&
          value.toString().indexOf(busqueda) !== -1
      }
      },
      //se crea al inicializar vue
      beforeCreate(){
          console.log('before create');
      },
      //cuando los datos ya se encuentran disponibles
      //se crean los metodos pero aun nose accede al dom
      created(){
          console.log("created")
      },
      //antes de montar el componente
      beforeMount(){
          console.log("Before Mount")
      },
      //cuando el componente ya se muestra
      mounted(){
          console.log("Mounted")
      },
      //al detectar cambios en los datos
      beforeUpdate(){
          console.log("Before Update")
      },
      //justo antes del desmontaje aunque el componente sigue siendo funcional
      beforeDestroy(){
          console.log("before Destroy")
      },
      //cuando el componente y sus hijos fueron desmontados
      destroyed(){
          console.log("destroyed")
      }
  }
</script>