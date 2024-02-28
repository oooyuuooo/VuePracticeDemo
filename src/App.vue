<template>
    <base-layout>
        <template v-slot:header>
            <nav class="navbar navbar-expand-lg fixed-top bg-body-tertiary">
                <div class="container-fluid">
                    <a class="navbar-brand" href="#">Vue</a>
                    <button
                        class="navbar-toggler"
                        type="button"
                        data-bs-toggle="collapse"
                        data-bs-target="#navbarSupportedContent"
                        aria-controls="navbarSupportedContent"
                        aria-expanded="false"
                        aria-label="Toggle navigation"
                    >
                        <span class="navbar-toggler-icon"></span>
                    </button>
                    <div
                        class="collapse navbar-collapse"
                        id="navbarSupportedContent"
                    >
                        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                            <li class="nav-item">
                                <router-link class="nav-link" to="/about"
                                    >使用說明</router-link
                                >
                            </li>
                            <li class="nav-item dropdown">
                                <a
                                    class="nav-link dropdown-toggle"
                                    href="#"
                                    role="button"
                                    data-bs-toggle="dropdown"
                                    aria-expanded="false"
                                >
                                    PracticeDemo
                                </a>
                                <ul class="dropdown-menu">
                                    <router-link
                                        class="dropdown-item"
                                        to="/practice"
                                        >v-if v-for</router-link
                                    >
                                    <li>
                                        <a class="dropdown-item" href="#"
                                            >Another action</a
                                        >
                                    </li>
                                    <li><hr class="dropdown-divider" /></li>
                                    <li>
                                        <a class="dropdown-item" href="#"
                                            >Something else here</a
                                        >
                                    </li>
                                </ul>
                            </li>
                        </ul>
                    </div>
                </div>
            </nav>
        </template>
        <router-view/>
        <template v-slot:footer>
            <div>
                <p>小歐的 Vue 練習 之 這裡是 footer</p>
            </div>
        </template>
    </base-layout>
</template>

<script setup>
import BaseLayout from './components/BaseLayout.vue'
</script>

<style lang="scss">
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
}

.navbar {
    padding: 5px;
    background: linear-gradient(315deg, #0b346e 25%, #a5dee4);
}
.wrapper{
    margin-top: 90px;
}
.myComponent {
    margin: 30px;
    width: auto;
    height: auto;
    display: flex;
    align-items: center;
    justify-content: center;
    background: linear-gradient(315deg, #0b346e 25%, #a5dee4);
    border-radius: 30px;
    padding: 10px;
}

.componentContainer {
    width: calc(100% - 0.1%);
    height: calc(100% - 0.1%);
    background: #ffffff;
    border-radius: 22px;
    overflow: hidden;
}

p {
    font-size: 20px;
    margin: 10px;
}
</style>
