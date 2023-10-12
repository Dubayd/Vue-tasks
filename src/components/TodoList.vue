<template>
    <div>
        <h1>To-Do Lijst</h1>
        <input v-model="newTodo" @keyup.enter="addTodo" placeholder="Maak een task!" />
        <ul>
            <li v-for="(todo, index) in todos" :key="index">
                {{ todo.text }}
                <button @click="removeTodo(index)">Verwijder</button>
            </li>
        </ul>
    </div>
</template>
  

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
