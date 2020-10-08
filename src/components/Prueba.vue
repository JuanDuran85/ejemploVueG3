<template>
  <div>
    <h1>Esto es un componente...</h1>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Rerum obcaecati ipsum molestiae doloremque a! Voluptates, id impedit mollitia corporis beatae voluptatum voluptas. Mollitia accusantium possimus explicabo, impedit saepe omnis deserunt!</p>
    <ul>
      <li v-for="(item,index) in usuarios" :key="index" @click="mostrarData(item.nombre)">{{index+1}} - {{item.nombre}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Prueba',
  data() {
    return {
      usuarios: [
            {nombre: "Juan", apellido: "Duran", edad: "35"},
            {nombre: "Manuel", apellido: "Romero", edad: "13"},
            {nombre: "Maria", apellido: "Perez", edad: "20"},
            {nombre: "Paola", apellido: "Rogriguez", edad: "50"},
            {nombre: "Marcos", apellido: "Soto", edad: "85"},
            {nombre: "Jocelyn", apellido: "Cerrano", edad: "30"},
        ],
    }
  },
  methods: {
    mostrarData(nombre){
      console.log(nombre);
    }
  },

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
