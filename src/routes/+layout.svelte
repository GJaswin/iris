<script lang="ts">
	import '../app.css';
	let { children } = $props();
</script>

<head>
	<title>Iris</title>
</head>

<header>
	<nav
		class="fixed flex w-[100%] flex-col rounded-b-lg bg-rose-100 p-3 md:h-[100%] md:max-w-[30%] md:rounded-e-lg"
	>
		<div class="flex items-center justify-between">
			<div
				class="nav-toggle cursor-pointer rounded-lg bg-rose-200 p-3 text-rose-800 transition-all ease-in-out hover:bg-rose-800 hover:text-white"
			>
				<i class="ri-menu-line text-3xl font-bold"></i>
			</div>
			<div class="logo flex items-center gap-2 text-rose-800">
				<i class="ri-eye-line text-4xl font-bold"></i>
				<h2 class="text-5xl font-bold">IRIS</h2>
			</div>
		</div>

		<div class=" hidden flex-col md:flex">
			<a href="/" class="nav-link">Home</a>
			<a href="/feed" class="nav-link">Camera Feed</a>
			<a href="/attendance" class="nav-link">Attendance</a>
			<a href="/animals" class="nav-link">Animal Detection</a>
		</div>
	</nav>
</header>

<main class="absolute top-[5rem] left-0 m-5 md:top-0 md:left-[30%]">
	{@render children()}
</main>

<style lang="scss">
	.logo {
		font-family: 'Iceland', sans-serif;
	}
</style>
