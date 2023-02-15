<svelte:head>
	<title>Signup | CodeShare</title>
</svelte:head>
<section class="mt-40 flex flex-col items-center">
	<h2 class="font-bold text-4xl mb-10">Signup</h2>
	<form>
		<div class="w-[400px]">
			<label for="username" class="block text-sm text-gray-800 mb-1">Username</label>
			<input
				type="text"
				name="username"
				id="username"
				placeholder="Enter your username"
				class="bg-gray-300 w-[400px] text-black py-2 px-3 rounded-lg outline-mainColour"
			/>
		</div>
		<div class="w-[400px] mt-5">
			<label for="email" class="block text-sm text-gray-800 mb-1">Email</label>
			<input
				type="email"
				name="email"
				id="email"
				placeholder="Enter your email"
				class="bg-gray-300 w-[400px] text-black py-2 px-3 rounded-lg outline-mainColour"
			/>
		</div>
		<div class="w-[400px] mt-5">
			<label for="password" class="block text-sm text-gray-800 mb-1">Password</label>
			<input
				type="password"
				name="password"
				id="password"
				placeholder="Enter your password"
				class="bg-gray-300 w-[400px] text-black py-2 px-3 rounded-lg outline-mainColour"
			/>
		</div>

		<div class="flex justify-end mt-5 ">
			<button class="w-fit bg-primary text-white px-7 py-2 rounded-lg">Signup</button>
		</div>
	</form>

	<div class="flex justify-start w-[400px] mt-5">
		<p>Already Registered? <a href="/login" class="font-bold">Login</a></p>
	</div>
</section>
