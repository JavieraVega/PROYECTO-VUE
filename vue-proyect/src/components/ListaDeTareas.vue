<template>
    <div>
        <h2>Lista de Tareas</h2>
        <input type="text" v-model="nuevaTarea" @keyup.enter="addTarea"/>  <!-- a este input se le asigna la variable reactiva - keyup: para que la función addTarea se ejecute al hacer enter, se le agrega.enter -->
        <ul>
            <li v-for="(item, index) in tareas" :key="index">  <!--para hacer el recorrido del array (tareas)--> 
                {{ item }}
            <button @click="borrarTarea(index)">Borrar</button>
            </li> 
         </ul>
    </div>
</template>

<script setup>
    import {ref} from 'vue';  // se importa ref para crear un objeto reactivo (actualiza)
    const tareas = ref ([]);  // este objteto se asigna a esta cte que inicia con un array vacío
    const nuevaTarea = ref(''); // se agrega cte ob de ref que parte vacío
    const  addTarea = () => {  // función que permite añadir tarea hacia abajo
        tareas.value.push(nuevaTarea.value);  //value = obtiene el valor de una variable reactiva. Pero como tareas es un array, para añadirle contenido se debe utilizar el método "push", cada vez que se se haga enter se añade una nueva tarea y para obtener el valor de esa tarea se le agrega nuevamente el value. 
        nuevaTarea.value = ''; // tenemos que hacer que el input nuevaTarea borre su valor
    }
    const borrarTarea = (index) => {
        tareas.value.splice(index,1);  // método splice, elimina 1 elemento del interior del array, le agregamos el 1 para indicar que se eliminará 1 elemento.

    }

</script>
<style></style>