<script>
	import { onMount } from 'svelte';

	/**
	 * @type {HTMLVideoElement | null}
	 */
	let videoSource = null;
	let loading = false;
	const obtainVideoCamera = async () => {
		try {
			loading = true;
			const stream = await navigator.mediaDevices.getUserMedia({
				video: true
			});
			// @ts-ignore
			videoSource.srcObject = stream;
			// @ts-ignore
			videoSource.play();
			loading = false;
		} catch (error) {
			console.log(error);
		}
	};

	onMount(() => {
		obtainVideoCamera();
	});
</script>

<head>
	<title>Camera Feeds</title>
</head>

<main>
	<div class="main-container">
		<div class="flex flex-col gap-3">
			<h2 class="text-2xl font-bold text-rose-800">Camera Feeds</h2>
			<div>
				{#if loading}
					<p>Loading Camera</p>
				{/if}
				<!-- svelte-ignore a11y-media-has-caption -->
				<video bind:this={videoSource} class="rounded-lg w-[100%]"></video>
			</div>
			<div class="h-[300px] rounded-lg bg-rose-200"></div>
			<div class="h-[300px] rounded-lg bg-rose-200"></div>
			<div class="h-[300px] rounded-lg bg-rose-200"></div>
		</div>
	</div>
</main>
