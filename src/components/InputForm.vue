<template>
    <div class="form-container">
        <form>
            <input v-model="newTodo" type="text" name="todo-input" />
        
            <button v-on:click.prevent="addTodo" class="button">Add</button>
        </form>
        <todo-list :todoArray="todoArray" v-on:change="deleteElem(keyOfArray)"/>
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
            keyOfArray: null,
        }
    },
    methods: {
        addTodo() {
            let todo = this.newTodo.trim();
            if (todo) {
                this.todoArray.push(todo);
            }
            this.newTodo = '';
        },
        deleteElem(keyOf) {
            this.todoArray.splice(keyOf, 1);
        }
    },
    computed: {
        
    },
}
</script>