<template>
    <transition>
        <div class="myComponent" id="practice" v-if="show">
            <div class="componentContainer">
                <input-form></input-form>
            </div>
        </div>
    </transition>
</template>

<script setup>
import { onMounted, ref } from 'vue';
import InputForm from '@/components/InputForm.vue';
const show = ref(false);

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
