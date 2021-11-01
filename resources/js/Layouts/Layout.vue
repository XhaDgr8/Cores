<template>
    <navbar />

    <main class="my-12 w-10/12 mx-auto relative">
        <slot></slot>
    </main>
</template>

<script setup>
    import navbar from "../Blocks/Headers/Header-1.vue"
</script>
