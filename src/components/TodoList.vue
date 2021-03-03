<template>
  <h1>Hello from the TodoList</h1>
</template>

<script>
import { todoItems } from "../data";

export default {
    data() {
        return {
        todos: [...todoItems],
        };
    },
}
</script>

<style>

</style>