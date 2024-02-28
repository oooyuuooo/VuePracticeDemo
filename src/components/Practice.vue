<template>
    <button @click="btnClick" class="btn btn-dark btn-sm mb-2">點我</button>
    <h6 v-if="result">TRUE</h6>
    <h6 v-else>FALSE😢</h6>
</template>

<script setup>
import { defineModel } from 'vue'

const result = defineModel()

function btnClick() {
    const randomNum = Math.random(0, 1)
    randomNum > 0.5 ? (result.value = true) : (result.value = false)
}
</script>
