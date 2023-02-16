<script>
	import '../app.css';
	import '@fontsource/inter/400.css';
	import '@fontsource/inter/500.css';
	import '@fontsource/inter/600.css';
	import '@fontsource/inter/700.css';
	import Navbar from '../components/Navbar.svelte';

	import { userId } from '../store/userInfo';
	import { getAuth, onAuthStateChanged } from 'firebase/auth';

	const auth = getAuth();
	onAuthStateChanged(auth, (user) => {
		if (user) {
			const uid = user.uid;
			$userId = uid;
		} else {
			$userId = null;
		}
	});
</script>

<Navbar />

<main class="max-w-[1180px] mx-auto">
	<slot />
</main>
