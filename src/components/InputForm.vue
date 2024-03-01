<template>
    <form class="myFrom">
        帳號:
        <input
            type="text"
            placeholder="Account"
            v-model="userAccount"
            class="mb-3 mt-2"
        />
        名字:
        <input type="text" placeholder="Name" v-model="userName" class="mb-3" />
        密碼:
        <input
            type="text"
            placeholder="Password"
            v-model="userPassword"
            class="mb-3"
        />
    </form>
    <button @click.prevent="submit" class="btn myBtn mb-2">送出</button>
    <div v-if="submitFrom">
        <p>
            帳號: {{ userAccount }}, 密碼: {{ userPassword }}, 名字:
            {{ userName }}
        </p>
    </div>
</template>

<script setup>
import { ref } from 'vue';
const userAccount = ref('');
const userName = ref('');
const userPassword = ref('');
const submitFrom = ref(false);
function submit() {
    if (confirm('要送出嗎?')) {
        (submitFrom.value = true), alert('謝謝');
    } else {
        (submitFrom.value = false), alert('可以繼續編輯內容');
    }
}
</script>
<style scoped>
.myForm {
    display: flex;
    align-items: center;
    justify-content: center;
}
input {
    border: 5px solid #0b346e;
    border-radius: 10px;
}
.myBtn {
    background-color: #0b346e;
    color: white;
}
</style>
