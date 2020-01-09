<template>
    <div class="form-container">
        <form>
            <input v-model="newTodo" type="text" name="todo-input" />
        
            <button v-on:click.prevent="addTodo" class="button">Add</button>
        </form>
        <todo-list :todoArray="todoArray" />
    </div>
</template>

<script>
import TodoList from "@/components/TodoList.vue";

export default {
    name: "InputForm",
    components: {
        TodoList,
    },
    data() {
        return {
            todoArray: [],
            newTodo: null,
        }
    },
    methods: {
        addTodo() {
            this.todoArray.push(this.newTodo);
        }
    },
    computed: {

    },
}
</script>