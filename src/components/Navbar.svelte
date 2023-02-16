<script>
	import { signOut } from 'firebase/auth';
	import { onMount } from 'svelte';
	import { userId } from '../store/userInfo';
	import { auth } from '../utils/firebase';
	let hamburgerIcon;
	let mobileNav;

	let mobileNavClasses = 'hidden';
	onMount(() => {});

	const onHamburgerClick = () => {
		hamburgerIcon.classList.toggle('active');
		mobileNav.classList.toggle('hidden');
		if (!mobileNav.classList.contains('hidden')) {
			mobileNavClasses =
				'flex flex-col h-fit items-center absolute top-20 bg-primary left-0 px-10 py-20 w-full ';
		}
		// mobileNav.classList.toggle(
		// 	'flex flex-col h-fit items-center absolute top-20 bg-black left-0 px-10 py-20 w-full '
		// );
	};

	const handleLogout = async () => {
		await signOut(auth);
	};
</script>

<header class="bg-primary h-[80px]">
	<div class="max-w-[1180px] mx-auto p-5 text-white flex justify-between items-center relative">
		<h1 class="text-2xl md:text-3xl font-bold">
			<a href="/"> EasyCodeShare </a>
		</h1>

		<nav class="hidden md:flex items-center gap-12 ">
			<ul class="flex gap-5 text-xl">
				<li>
					<a href="/">Home</a>
				</li>
				<li>
					<a href="/about">About</a>
				</li>
			</ul>

			{#if $userId !== null}
				<button
					class=" border-2 font-bold border-white rounded-lg px-7 py-2"
					on:click={() => handleLogout()}>Logout</button
				>
			{:else}
				<a href="/login" class=" border-2 font-bold border-white rounded-lg px-7 py-2">Login</a>
			{/if}
		</nav>

		<nav class={`" ${mobileNavClasses} md:hidden`} bind:this={mobileNav}>
			<ul class="flex flex-col gap-5 text-xl">
				<li>
					<a href="/">Home</a>
				</li>
				<li>
					<a href="/about">About</a>
				</li>
			</ul>

			{#if $userId !== null}
				<button
					class=" border-2 font-bold border-white rounded-lg px-7 py-2 mt-5"
					on:click={() => handleLogout()}>Logout</button
				>
			{:else}
				<a href="/login" class=" border-2 font-bold border-white rounded-lg px-7 py-2 mt-5">Login</a
				>
			{/if}
		</nav>

		<div
			class="hamburger block md:hidden cursor-pointer"
			bind:this={hamburgerIcon}
			on:click={onHamburgerClick}
		>
			<span class="bar" />
			<span class="bar" />
			<span class="bar" />
		</div>
	</div>
</header>

<style>
	.bar {
		display: block;
		width: 25px;
		height: 3px;
		margin: 5px auto;
		background-color: white;
	}
	/* 
	@media (max-width: 768px) { */
	/* div.hamburger.active span.bar:nth-child(2) {
			opacity: 0;
		}
		.hamburger.active .bar:nth-child(1) {
			transform: translateY(8px) rotate(45deg);
		}
		.hamburger.active .bar:nth-child(3) {
			transform: translateY(-8px) rotate(-45deg);
		} */
	/* } */
</style>
