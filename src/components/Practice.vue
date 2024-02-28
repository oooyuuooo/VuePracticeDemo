<template>
    <button @click="btnClick" class="btn btn-dark">點我</button>
    <h1 v-if="result">TRUE</h1>
    <h1 v-else>FALSE😢</h1>
</template>

<script setup>
import { defineModel } from 'vue'

const result = defineModel()

function btnClick() {
    const randomNum = Math.random(0, 1)
    randomNum > 0.5 ? (result.value = true) : (result.value = false)
}
</script>
