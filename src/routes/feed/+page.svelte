<script>
	import { onMount } from 'svelte';

	// @ts-ignore
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

<div>
	{#if loading}
		<h1>Loading Camera</h1>
	{/if}
	<!-- svelte-ignore a11y-media-has-caption -->
	<video bind:this={videoSource} class="rounded-lg"></video>
</div>
