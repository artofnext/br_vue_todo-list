<template>
    <div>
        <ul>
            <li v-for="(value, index) in todoArray" :key="index">
                {{ index + 1 }} - {{ value }}
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: "TodoList",
    props: {
        todoArray: Array,
    },
}
</script>