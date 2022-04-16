<script>
export default {
    data() {
        return {
            todo: '',
            todos: [],
        }
    },
    methods: {
        saveTodo() {
            this.todos.push(this.todo);
            this.todo = '';
        },
        deleteTodo(index) {
            this.todos.splice(index, 1)
        }
    }
}
</script>

<template>

<section>
    <section class="todo">
        <h1 class="title">Todo List App</h1>
        <p>Create a list of task</p>
        <div class="action">
            <input class="input" v-model="todo">
            <button class="save" @click="saveTodo()">Save</button>
        </div>
    </section>

    <section class="list">
        <div class="task" v-for="(todo, index) in todos">
            <div class="content">{{ todo }}</div>
            <button class="delete" @click="deleteTodo(index)">Delete</button>
        </div>
    </section>
</section>

</template>

<style scoped>
    .title {
        font-size: 50px;
        margin-bottom: 10px;
    }

    .action {
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .input {
        border: none;
        outline: none;
        border-bottom: 1px solid #fff;
        background-color: transparent;
        color: #fff;
        font-size: 25px;
        padding: 10px 0;
    }
</style>