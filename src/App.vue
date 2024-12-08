<script setup>
import Footer from './components/Footer.vue'
import IEEE_WCCI_2024 from "@/Views/IEEE_WCCI_2024.vue";

import {ref, computed} from 'vue'
import NotFound from "@/Views/NotFound.vue";

const routes = {
    '/': IEEE_WCCI_2024,
    // '/about': About
}

const currentPath = ref(window.location.hash)

window.addEventListener('hashchange', () => {
    currentPath.value = window.location.hash
})

const currentView = computed(() => {
    return routes[currentPath.value.slice(1) || '/'] || NotFound
})
</script>

<template>
    <nav
        id="navbar"
        class="sticky top-0 z-10 flex bg-blue-900 p-2 text-white gap-3"
    >
        <a href="#/">
            Home
        </a>
        <a href="#/about_us">
            About us
        </a>
    </nav>

    <component :is="currentView"/>

    <footer>
        <Footer/>
    </footer>
</template>

<style scoped>
</style>
