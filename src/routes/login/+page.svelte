<script>
	import { enhance } from '$app/forms';
</script>

<svelte:head>
	<title>Login | CodeShare</title>
</svelte:head>
<section class="mt-36 flex flex-col items-center">
	<h2 class="font-bold text-4xl mb-10">Login</h2>
	<form>
		<div class="md:w-[400px] w-full">
			<label for="username" class="block text-sm text-gray-800 mb-1">Username</label>
			<input
				type="text"
				name="username"
				id="username"
				placeholder="Enter your username"
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

		<div class="flex justify-end mt-5 ">
			<button class="w-fit bg-primary text-white px-7 py-2 rounded-lg">Login</button>
		</div>
	</form>

	<div class="flex justify-start md:w-[400px] mt-5">
		<p>Not Registered? <a href="/signup" class="font-bold">Signup</a></p>
	</div>
</section>
