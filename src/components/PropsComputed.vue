<template>
    <div class="div__computed">
        {{ fullName }}

        <h2>Todos em aberto</h2>
        <div v-for="todo in uncompletedTodos" :key="todo.id">{{  todo.title }}</div>
        <br><br>
        <h2>Todos completas</h2>
        <div v-for="todo in completedTodos" :key="todo.id">{{ todo.title }}</div>
        <br><br>
        <h2>Todos</h2>
        <!-- Tem checkBox que já vai está selecionado porque um "todo" vai ter o 'completed' 
            com o valor TRUE -->
            <!-- Ao clicar muda o valor para true ou flase, fazendo com que mude os 
            valores de lugar, de "Todo em aberto" para "Todos completas" -->
        <div v-for="todo in todos" :key="todo.id">
            <input type="checkbox" v-model="todo.completed">
            {{ todo.title }}
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            user: {
                first_name: 'Thommy',
                last__name: 'Shelby'
            },
            todos: [
                {
                    "userId": 1,
                    "id": 1,
                    "title": "Recheado de chocolate",
                    "completed": false,
                },
                {
                    "userId": 1,
                    "id": 2,
                    "title": "Coca cola espumante sem gás",
                    "completed": false,
                },
                {
                    "userId": 1,
                    "id": 3,
                    "title": "Bolacha de recheado sem recheo",
                    "completed": false
                },
                {
                    "userId": 1,
                    "id": 4,
                    "title": "Porco assado sem fogo frio",
                    "completed": true
                },
                {
                    "userId": 1,
                    "id": 5,
                    "title": "Desenvolvedor full stack de algum coisa",
                    "completed": false
                }
            ]
        }
    },
    computed: {
        fullName() {
            return `${this.user.first_name}  ${this.user.last__name}`
        },
        completedTodos() {
            return this.todos.filter(todos => todos.completed)
        },
        uncompletedTodos() {
            return this.todos.filter(todos => !todos.completed)
        }
    }
}
</script>
    
<style>
    .div__computed{
        border: 2px solid green;
        margin: 10px 0;
    }
</style>