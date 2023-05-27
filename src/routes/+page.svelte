<script>
	import { fly } from 'svelte/transition';

	import TheMain from '$lib/components/TheMain.svelte';
	import OffCanvas from '$lib/components/OffCanvas.svelte';

	let showOffCanvas = false;

	function toggleOffCanvas() {
		showOffCanvas = !showOffCanvas;
	}
</script>

<div class="wrapper">
	<div class="container">
		{#if showOffCanvas}
			<div transition:fly={{ x: -200, duration: 1000 }} class="canvas-wrapper">
				<OffCanvas on:toggleOffCanvas={toggleOffCanvas} />
			</div>
		{/if}
		<TheMain on:toggleOffCanvas={toggleOffCanvas} />
	</div>
</div>

<style>
	.canvas-wrapper {
		position: absolute;
	}
	.wrapper {
		background-image: linear-gradient(238.71deg, #bd00ff 7.63%, #00a3ff 117.53%);
		padding-inline: 1.6rem;
		padding-block: 1.2rem;
		min-height: 100vh;
	}

	.container {
		height: 100%;
		width: 100%;
		background-color: #221f26;
		border-radius: 1.3rem;
		min-height: 87.2rem;
	}
</style>
