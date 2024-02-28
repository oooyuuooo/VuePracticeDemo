<template>
    <div>
        <input type="text" placeholder="TodoList" required v-model="newTodo" />
        <button @click.prevent="addTodo" class="btn btn-dark addBtn">
            Add
        </button>
        <button
            @click="hideCompleted = !hideCompleted"
            class="btn btn-dark ms-2"
        >
            {{ hideCompleted ? 'Show All' : 'Not Yet' }}
        </button>
    </div>
    <ul>
        <div class="list">
            <li v-for="todo in filteredTodos" :key="todo.id">
                <div class="listItem">
                    <input
                        type="checkbox"
                        v-model="todo.done"
                        class="mb-2 check"
                    />
                    <p :class="{ done: todo.done }">{{ todo.text }}</p>
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
import { defineModel, ref, computed } from 'vue'
const newTodo = defineModel()
const hideCompleted = ref(false)
let id = 0
const todos = ref([
    { id: id++, text: 'Todo1', done: true },
    { id: id++, text: 'Todo2', done: false }
])

const filteredTodos = computed(() => {
    return hideCompleted.value
        ? todos.value.filter((todo) => !todo.done)
        : todos.value
})

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
    border: 5px solid #0b346e;
    border-radius: 10px;
    padding: 5px;
}
.addBtn,
.removeBtn {
    margin-left: 10px;
}
.list {
    list-style: none;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    .listItem {
        display: flex;
        justify-content: center;
        align-items: center;
    }
}
.done {
    text-decoration: line-through;
}
.check {
    margin: 10px;
}
</style>
