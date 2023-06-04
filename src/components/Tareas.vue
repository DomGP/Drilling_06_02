<template>
    <div class="div-style">
        <h1>Lista de Tareas</h1>
        <form class="form-style">
            <div class="mb-3">
                <input type="text" class="form-control" id="name" v-model="tarea" placeholder="Ingresa una tarea">
                <button type="submit" @click.prevent="agregarTareas" class="btn btn-primary">Agregar</button>
                <ul v-for="(tarea,index) in tareas" :key="index">
                    <li>{{tarea}} 
                        <button class="btn btn-primary" type="" @click.prevent="eliminarTareas(index)">Eliminar</button> 
                        <button class="btn btn-info" type="" @click.prevent="editarTareas(index)">Editar</button>
                    </li>
                </ul>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    name: 'Test-comp',
    // props: {},
    data: function(){
        return {
            tarea:"",
            tareas:[],
        }
    },
    // computed: {},
    methods: {
        agregarTareas(){
            this.tareas.push(this.tarea)
            this.tarea=""
        },
        eliminarTareas(index){
            this.tareas.splice(index,1)

        },
        editarTareas(index){
            let tareaEditada=prompt('Editar tarea',this.tareas[index])
            this.tareas.splice(index,1,tareaEditada)
        }
    }
    // watch: {},
    // components: {},
    // mixins: [],
    // filters: {},
    // -- Lifecycle Methods
    // -- End Lifecycle Methods
}
</script>

<style scoped>
.div-style{
    margin-left: 50px;
}
h1{
    margin-bottom: 30px;
}
.form-style{
    width: 30%;
}
.btn{
    margin-top: 10px;
    margin-right: 5px;
}
</style>