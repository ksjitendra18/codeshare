<script>
	import '../app.css';
	import '@fontsource/inter/400.css';
	import '@fontsource/inter/500.css';
	import '@fontsource/inter/600.css';
	import '@fontsource/inter/700.css';
	import Navbar from '../components/Navbar.svelte';
</script>

<Navbar />

<main class="max-w-[1180px] mx-auto">
	<slot />
</main>
