<template>
  <div>
    <h1>Esto es un componente...</h1>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Rerum obcaecati ipsum molestiae doloremque a! Voluptates, id impedit mollitia corporis beatae voluptatum voluptas. Mollitia accusantium possimus explicabo, impedit saepe omnis deserunt!</p>
    <ul>
      <li v-for="(item,index) in usuarios" :key="index" @click="mostrarData(item.nombre)">{{index+1}} - {{item.nombre}}</li>
    </ul>
    <div v-if="nombres.length > 0">
      <h2>Usuarios con clic</h2>
      <ul>
        <li v-for="(item,index) in nombres" :key="index">{{item}}</li>
      </ul>
    </div>
    <hr>
    <form @submit.prevent="agregarTarea">
      <label for="tarea">Ingrese la Tarea</label>
      <input type="text" v-model="tarea">
      <button type="submit">Agregar</button>
    </form>
    <div v-if="tareas.length > 0">
      <ul>
        <li v-for="(task,index) in tareas" :key="index">{{task }} <button @click="eliminar(index)" class="elimina">Eliminar</button> </li>
      </ul>
    </div>
    <div v-else class="noTarea">
      <h3>Agrega una tarea y haz clic sobre el botón</h3>
    </div>
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
      nombres: [],
      tarea: '',
      tareas: []
    }
  },
  methods: {
    mostrarData(nombre){
      let resultado = this.nombres.find(res => res == nombre);
      console.log(resultado);
      if (!resultado){
        this.nombres.push(nombre);
      }
    },
    agregarTarea(){
      this.tareas.push(this.tarea);
      this.tarea = '';
    },
    eliminar(valor){
      let confirmado = confirm("Estas seguro que deseas borrar la tarea????")
      console.log(confirmado);
      if (confirmado){
        this.tareas.splice(valor,1);
        alert("Se eliminó...");
      }
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.noTarea{
  background-color: yellowgreen;
  font-size: 20px;
  font-weight: 900;
  width: 50%;
  height: 100px;
}
.elimina{
  background-color: red;
  font-size: 24px;
  width: 100px;
  height: 50px;
}
</style>
