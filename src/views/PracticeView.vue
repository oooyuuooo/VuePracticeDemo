<template>
    <div class="myComponent" id="practice">
        <div class="componentContainer">
            <p><strong>v-if v-else</strong></p>
            <Practice v-bind="{ result }" class="btn"></Practice>
        </div>
    </div>
    <div class="myComponent" id="todoList">
        <div class="componentContainer">
            <p><strong>TodoList</strong></p>
            <TodoList></TodoList>
        </div>
    </div>
    <div class="myComponent" id="todoList">
        <div class="componentContainer">
            <p><strong>TodoList With Computed</strong></p>
            <ComputedTodoList></ComputedTodoList>
        </div>
    </div>
</template>

<script setup>
import Practice from '@/components/Practice.vue'
import TodoList from '@/components/TodoList.vue'
import ComputedTodoList from '@/components/ComputedTodoList.vue'
import { ref } from 'vue'
const result = ref(true)
</script>

<style scoped></style>
