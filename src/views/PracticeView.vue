<template>
    <transition>
        <div class="myComponent" id="practice" v-if="show">
            <div class="componentContainer">
                <p><strong>v-if v-else</strong></p>
                <Practice v-bind="{ result }" class="btn"></Practice>
            </div>
        </div>
    </transition>
    <transition>
        <div class="myComponent" id="todoList" v-if="show">
            <div class="componentContainer">
                <p><strong>TodoList</strong></p>
                <TodoList></TodoList>
            </div>
        </div>
    </transition>
    <transition>
        <div class="myComponent" id="todoList" v-if="show">
            <div class="componentContainer">
                <p><strong>TodoList With Computed</strong></p>
                <ComputedTodoList></ComputedTodoList>
            </div>
        </div>
    </transition>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import Practice from '@/components/Practice.vue';
import TodoList from '@/components/TodoList.vue';
import ComputedTodoList from '@/components/ComputedTodoList.vue';
const show = ref(false);
const result = ref(true);

//在 loding 頁面的時候觸發
//生命週期函數
onMounted(() => {
    show.value = true;
});
</script>

<style scoped>
/* 下面我们会解释这些 class 是做什么的 */
.v-enter-active,
.v-leave-active {
    transition: opacity 1s ease;
}

.v-enter-from,
.v-leave-to {
    opacity: 0;
}
</style>
