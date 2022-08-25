<template>
    <div>
        <h1 class="display-4 text-center">Listado de tareas</h1>
        <hr>
        <div class="row">
            <div class="col-lg-8 offset-lg-2">
                <div class="card mt-4">
                    <div class="card-body">
                        <div class="input-group">
                            <input type="text" v-model="tarea" class="form-control form-control-sm" placeholder="Agregar tarea">
                            <div class="inpt-group-append">
                                <button v-on:click="agregarTarea()" class="btn btn-success btn-sm">Agregar</button>
                            </div>
                        </div>
                        <br>
                        {{listTarea}}
                        <ul class="list-group">
                            <li class="list-group-item d-flex justify-content-between">
                                <span class="cursor">
                                    <i class="bi bi-circle"></i>
                                </span>
                                Hacer la tarea
                                <span class="text-danger cursor">
                                    <i class="bi bi-trash"></i>
                                </span>
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Tarea-1',
        data() {
            return{
                tarea: '',
                listTarea: []
            }
        },
        methods: {
            agregarTarea(){
                const tarea ={
                    nombre : this.tarea,
                    estado : false
                }
                this.listTarea.push(tarea);
                this.tarea='';
            }
        }
    }
</script>

<style scoped>
    .cursor:hover{
        cursor: pointer;
    }
</style>

