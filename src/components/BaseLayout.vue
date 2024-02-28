<!-- BaseLayout.vue -->
<template>
    <header>
        <slot name="header"></slot>
    </header>
    <main class="wrapper">
        <slot></slot>
    </main>
    <footer class="footer">
        <slot name="footer"></slot>
    </footer>
</template>

<script setup></script>
