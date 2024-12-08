<script setup>
import Footer from './components/Footer.vue'
import IEEE_WCCI_2024 from "@/Views/IEEE_WCCI_2024.vue";

import {ref, computed} from 'vue'
import NotFound from "@/Views/NotFound.vue";
import INNS_IJCNN_2025 from "@/Views/INNS_IJCNN_2025.vue";

const routes = {
    '/': {
        name: 'INNS IJCNN 2025',
        view: INNS_IJCNN_2025
    },
    '/IEEE/WCCI/2024': {
        name: 'IEEE WCCI 2024',
        view: IEEE_WCCI_2024
    }
    // '/about': About
}

const notFoundRoute = {
    name: '404: Not Found',
    view: NotFound
}

const currentPath = ref(window.location.hash)

window.addEventListener('hashchange', () => {
    currentPath.value = window.location.hash
})

const currentView = computed(() => {
    let route = routes[currentPath.value.slice(1) || '/'] || notFoundRoute
    return route.view
})
</script>

<template>
    <nav
        id="navbar"
        class="sticky top-0 z-10 flex bg-blue-900 px-2 text-white gap-3"
    >
        <a
            v-for="route in Object.keys(routes)"
            :href="'#' + route"
            :class="currentPath === '#' + route
                ? 'bg-blue-700'
                : 'text-blue-300 hover:bg-blue-800'"
            class="p-2 text-white no-underline hover:text-white"
        >
            {{ routes[route].name }}
        </a>
    </nav>

    <component :is="currentView"/>

    <footer>
        <Footer/>
    </footer>
</template>
