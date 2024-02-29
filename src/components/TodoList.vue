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
import { ref } from 'vue';
const newTodo = ref('');
let id = 0;
const todos = ref([
    { id: id++, text: 'Todo1' },
    { id: id++, text: 'Todo2' },
]);

function addTodo() {
    if (newTodo.value != '') {
        todos.value.push({
            id: id++,
            text: newTodo.value,
        });
    } else {
        alert('請輸入內容');
    }
    newTodo.value = '';
}
function removeTodo(todo) {
    todos.value = todos.value.filter((target) => target != todo);
}
</script>

<style scoped>
input {
    height: 50px;
    margin-bottom: 10px;
    border: 5px solid #0b346e;
    border-radius: 10px;
    padding: 5px;
}
.addBtn,
.removeBtn {
    margin-left: 10px;
}
.list {
    list-style: circle;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.listItem {
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>
