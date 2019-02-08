<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8 mt-4">
                <div class="card">
                    <div class="card-header">Task List</div>

                    <div class="card-body">
                        <ul>
                            <li v-for="task in tasks">{{task.title}}</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </div>

</template>

<script>
    export default {
        data(){
            return {
                tasks:[]
            }
        },
        created() {
            axios.get('./api/task')
            .then(response => this.tasks = response.data);
        },
        
    }
</script>

<style>
    
</style>
