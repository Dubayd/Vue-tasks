<template>
    <div class="container">
        <h1 class="heading">To-Do Lijst</h1>
        <input class="input" v-model="newTodo" @keyup.enter="addTodo" placeholder="Maak een task!" />
        <ul class="list">
            <li v-for="(todo, index) in todos" :key="index">
                {{ todo.text }}
                <button class="remove" @click="removeTodo(index)">X</button>
            </li>
        </ul>
    </div>
</template>

<style>
body {
    padding: 0px;
    margin: 0px;
}

.container {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
}

.heading {
    font-size: 24px;
    font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
    color: #333;
    margin-bottom: 10px;
    color: rgb(17, 165, 214);
}

.remove {
    border: none;
    border-radius: 20%;
    background-color: red;
}

.input {
    width: 30%;
    padding: 10px;
    border: 1px solid rgb(17, 165, 214);
    border-radius: 5px;
    margin-bottom: 10px;
}

.list {
    list-style-type: none;
    padding: 0;
}

.list li {
    margin: 5px 0;
    padding: 7px;
    color: rgb(17, 165, 214);
    font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
}

ul {
    border: 2px solid rgb(17, 165, 214);
    border-radius: 8px;
    width: 30%;
}

</style>
  

<script>
export default {
    data() {
        return {
            todos: [],
            newTodo: ''
        };
    },
    methods: {
        addTodo() {
            this.todos.push({ text: this.newTodo, completed: false });
            this.newTodo = '';
        },
        removeTodo(index) {
            this.todos.splice(index, 1);
        }
    }
};
</script>
