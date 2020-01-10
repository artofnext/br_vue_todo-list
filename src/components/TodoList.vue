<template>
    <div>
        <ul>
            <li v-for="(value, index) in todoArray" :key="index">
                <p>{{ index + 1 }} - {{ value }}<button v-on:click="deleteItem(index)">x</button></p>
            </li>
        </ul>
        <p>All Todo: {{ allTodo }}</p>
    </div>
</template>

<script>
export default {
    name: "TodoList",
    props: {
        todoArray: Array,
    },

    methods: {
        deleteItem (ind) {
            // this.todoArray.splice(ind, 1);
            this.$emit("change", ind);

        }
    },

    computed: {
        allTodo() {
            return this.todoArray.length ? this.todoArray.length : 0;
        }
    },
}
</script>

