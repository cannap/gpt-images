<script lang="ts">
	import '../app.scss';
	import { page } from '$app/stores';

	import { base } from '$app/paths';
	import { text } from '@sveltejs/kit';

	$: isActive = (route: string) => {
		return $page.route.id === route;
	};
</script>

<nav class="flex gap-3 fixed w-full top-0 bg-red-400">
	<a class:text-red-600={isActive('/')} href="{base}/">Index</a>
	<a class:text-red-600={isActive('/test')} href="{base}/test">Test page</a>
</nav>
<div class="flex flex-col h-screen">
	<header class="bg-red-500">header</header>
	<main class="bg-green-500 flex-grow"><slot /></main>
	<footer class="bg-blue-500">footer</footer>
</div>
