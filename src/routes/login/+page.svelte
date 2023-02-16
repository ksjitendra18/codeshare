<script>
	import { signInWithEmailAndPassword } from 'firebase/auth';
	import { auth } from '../../utils/firebase';
	import { userId } from '../../store/userInfo';
	let errorMessage = null;

	async function handleSubmit(event) {
		const data = new FormData(this);
		errorMessage = null;
		const userName = data.get('username');
		const email = data.get('email');
		const password = data.get('password');

		try {
			const userDetails = await signInWithEmailAndPassword(auth, email, password);
			console.log('userDetails', userDetails.user);
			$userId = userDetails.user.uid;
		} catch (error) {
			console.log('error in login', error.message);
			errorMessage = 'Please check your email and password.';
		}
	}
</script>

<svelte:head>
	<title>Login | CodeShare</title>
</svelte:head>
<section class="mt-36 flex flex-col items-center">
	<h2 class="font-bold text-4xl mb-10">Login</h2>
	<form method="POST" on:submit|preventDefault={handleSubmit}>
		<div class="md:w-[400px] w-full">
			<label for="email" class="block text-sm text-gray-800 mb-1">Email</label>
			<input
				type="text"
				name="email"
				id="email"
				placeholder="Enter your email"
				class="bg-gray-300 md:w-[400px]  text-black py-2 px-3 rounded-lg outline-mainColour"
			/>
		</div>
		<div class="md:w-[400px] mt-5">
			<label for="password" class="block text-sm text-gray-800 mb-1">Password</label>
			<input
				type="password"
				name="password"
				id="password"
				placeholder="Enter your password"
				class="bg-gray-300 md:w-[400px]  text-black py-2 px-3 rounded-lg outline-mainColour"
			/>
		</div>

		{#if errorMessage != null}
			<div class="bg-red-900 mt-7 px-5 py-2 rounded-xl text-white">{errorMessage}</div>
		{/if}

		<div class="flex justify-end mt-5 ">
			<button class="w-fit bg-primary text-white px-7 py-2 rounded-lg">Login</button>
		</div>
	</form>

	<div class="flex justify-start md:w-[400px] mt-5">
		<p>Not Registered? <a href="/signup" class="font-bold">Signup</a></p>
	</div>
</section>
