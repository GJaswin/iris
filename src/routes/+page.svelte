<!-- <script>
	// import nodejs bindings to native tensorflow,
	// not required, but will speed up things drastically (python required)
	// import '@tensorflow/tfjs-node';

	// implements nodejs wrappers for HTMLCanvasElement, HTMLImageElement, ImageData
	import * as canvas from 'canvas';

	import * as faceapi from 'face-api.js';

	// patch nodejs environment, we need to provide an implementation of
	// HTMLCanvasElement and HTMLImageElement
	const { Canvas, Image, ImageData } = canvas;
	// @ts-ignore
	faceapi.env.monkeyPatch({ Canvas, Image, ImageData });
</script> -->

<head>
	<title>Home</title>
</head>

<main>
	<div class="main-container">Content</div>
</main>
