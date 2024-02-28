<template>
    <div>
        <input type="text" placeholder="TodoList" required v-model="newTodo" />
        <button @click.prevent="addTodo" class="btn btn-dark addBtn">
            Add
        </button>
    </div>
    <ul>
        <div class="list">
            <li v-for="todo in todos" :key="todo.id">
                <div class="listItem">
                    <p>{{ todo.text }}</p>
                    <button
                        @click="removeTodo(todo)"
                        class="btn btn-dark btn-sm removeBtn"
                    >
                        Remove
                    </button>
                </div>
            </li>
        </div>
    </ul>
</template>

<script setup>
import { defineModel, ref } from 'vue'
const newTodo = defineModel()
const todos = ref([])
let id = 0

function addTodo() {
    if (newTodo.value != '') {
        todos.value.push({
            id: id++,
            text: newTodo.value
        })
    } else {
        alert('請輸入內容')
    }
    newTodo.value = ''
}
function removeTodo(todo) {
    todos.value = todos.value.filter((target) => target != todo)
}
</script>

<style scoped>
input {
    height: 50px;
    margin-bottom: 10px;
}
.addBtn,
.removeBtn {
    margin-left: 10px;
}
.list {
    list-style: circle;
    .listItem {
        display: flex;
        justify-content: start; 
        align-items: start; 
    }
}
</style>
