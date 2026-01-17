<script setup>
	import { ref, computed } from 'vue';

	import NotFound from '@/Views/NotFound.vue';
	import Footer from './components/Footer.vue';

	import IEEE_WCCI_2024 from '@/Views/IEEE_WCCI_2024.vue';
	import INNS_IJCNN_2025 from '@/Views/INNS_IJCNN_2025.vue';
	import INNS_IJCNN_2026 from '@/Views/INNS_IJCNN_2026.vue';
	import WCCI_WORKSHOP_2026 from './Views/WCCI_WORKSHOP_2026.vue';

	const BASE_SITE_NAME = 'AI Law and Regulation';

	const routes = {
		'/': {
			name: 'INNS IJCNN 2026',
			description:
				'International Joint Conference on Neural Networks (IJCNN) Maastricht 2026: Special Session "AI, Law and Regulation".',
			view: INNS_IJCNN_2026,
		},
		'WCCI-Workshop/2026': {
			name: 'WCCI Workshop 2026',
			description: '',
			view: WCCI_WORKSHOP_2026,
		},
		'/INNS_IJCNN/2025': {
			name: 'INNS IJCNN 2025',
			description:
				'International Joint Conference on Neural Networks (IJCNN) Rome 2025: Special Session "AI, Law and Regulation".',
			view: INNS_IJCNN_2025,
		},
		'/IEEE/WCCI/2024': {
			name: 'IEEE WCCI 2024',
			description:
				'IEEE World Congress on Computational Intelligence (WCCI) japan 2024: Special Session "AI, Law and Regulation".',
			view: IEEE_WCCI_2024,
		},
		'WCCI-Workshop/2026': {
			name: 'WCCI Workshop 2026',
			description: '',
			view: WCCI_WORKSHOP_2026,
		},
		// '/about': About
	};

	const notFoundRoute = {
		name: '404: Not Found',
		view: NotFound,
	};

	const currentPath = ref(window.location.hash);
	const description = ref('Special Session "AI, Law and Regulation".');

	window.addEventListener('hashchange', () => {
		currentPath.value = window.location.hash;
	});

	const currentView = computed(() => {
		let route = routes[currentPath.value.slice(1) || '/'] || notFoundRoute;
		document.title = BASE_SITE_NAME + ' | ' + route.name;
		description.value = route.description;
		return route.view;
	});
</script>

<template>
	<teleport to="head">
		<title>{{ title }}</title>
		<meta
			property="og:description"
			:content="description"
		/>
		<meta
			property="description"
			:content="description"
		/>
		<meta
			name="description"
			:content="description"
		/>
	</teleport>
	<nav
		id="navbar"
		class="sticky top-0 z-10 flex bg-primary-800 px-2 text-white gap-3"
	>
		<a
			v-for="route in Object.keys(routes)"
			:href="'#' + route"
			:class="
				currentPath === '#' + route
					? 'bg-primary-600'
					: 'text-primary-300 hover:bg-primary-700'
			"
			class="p-2 text-white no-underline hover:text-white"
		>
			{{ routes[route].name }}
		</a>
	</nav>

	<component :is="currentView" />

	<footer>
		<Footer />
	</footer>
</template>
