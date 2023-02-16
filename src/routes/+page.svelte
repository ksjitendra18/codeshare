<script>
	import { userId } from '../store/userInfo';
	console.log('user', $userId);
</script>

<svelte:head>
	<title>CodeShare</title>
</svelte:head>
<section class="mt-48 flex flex-col items-center justify-center">
	<h2 class="font-semibold text-3xl text-center md:text-4xl">
		Create and share code snippets easily.
	</h2>

	<a href="/login">
		<button class="mt-8 bg-primary px-7 md:px-10 py-4 rounded-lg font-semibold text-white">
			Start Creating
		</button>
	</a>
</section>
