<template>
    <div class="myComponent" id="practice">
        <div>
            <p><strong>v-if v-else Practice</strong></p>
            <Practice v-bind="{ result }" class="btn"></Practice>
        </div>
    </div>
    <div class="myComponent" id="todoList">
        <div>
            <p><strong>TodoList Practice</strong></p>
            <TodoList></TodoList>
        </div>
    </div>
</template>

<script setup>
import Practice from '@/components/Practice.vue'
import TodoList from '@/components/TodoList.vue'
import { ref } from 'vue'
const result = ref(true)
</script>

<style scoped>
.myComponent {
    margin: 10px;
    border: 2px solid blueviolet;
    border-radius: 10px;
    width: auto;
    height: auto;
    display: flex;
    display: flex;
    align-items: center;
    justify-content: center;
    p {
        font-size: 20px;
        margin: 10px;
    }
}
</style>
