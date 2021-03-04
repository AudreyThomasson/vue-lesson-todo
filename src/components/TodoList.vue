<template>
  <div>
    <h3>ToDo List</h3>
    <p>{{ itemsRemainingMessage }}</p>
    <div v-for="item in todos" :key="item.id">
      <TodoItem :todo="item" @status-change="handleStatusChange"/>
    </div>
  </div>
</template>

<script>
import { todoItems } from "../data";
import TodoItem from "./TodoItem.vue";

export default {
    components: { TodoItem },

    data() {
        return {
            todos: [...todoItems],
        };
    },

    methods: {
        handleStatusChange(item) {
            item.complete = !item.complete;
            console.log(item);
        },
    },
    computed: {
        itemsRemainingMessage() {
            const remaining = this.todos.filter((t) => !t.complete).length
            if (remaining == 1) {
                return "There is 1 item left to do today.";
            } 
            return `There are ${remaining} items left to do today.`;    
        
        },
    },
};

</script>

<style>

</style>