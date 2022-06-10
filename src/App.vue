<template>
    <div id="app">
        <h1 class="fw-bold">{{title}}</h1>
        <div class="d-flex justify-content-center mt-3">
            <h4 class="fw-bold text-primary m-0 me-3">{{subtitle01}}</h4>
            <input type="text" v-model="tarea_ingresada">
            <button class="ms-3 px-2 btn-success" @click="addToDo">Crear</button>
        </div>
        <div class="d-flex flex-column align-items-center mt-5">
            <h3 class="mt-5 text-danger fw-bold">{{subtitle02}}</h3>
            <ul>
                <li class="text-start fs-4" v-for="(tareA, index) in lista_tareas" :key="index">{{tareA}}</li>
            </ul>
        </div>
    </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
    export default {
        name: 'App',
        data(){
            return {
                title: "Crear una nueva Tarea",
                subtitle01: "Tarea: ",
                subtitle02: "Lista de Actividades por realizar:",
                tarea_ingresada: "",
                lista_tareas: []
            }
        },
        components: {
//      HelloWorld
        },
        methods: {
            addToDo() {
                this.lista_tareas.push(this.tarea_ingresada)
                console.log(this.lista_tareas)
                this.tarea_ingresada = ""
            }
        }
    }
</script>

<style>
    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 120px;
    }   
</style>