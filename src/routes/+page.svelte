<script>
	import { onMount, onDestroy } from 'svelte';
	import { fly } from 'svelte/transition';

	import TheMain from '$lib/components/TheMain.svelte';
	import OffCanvas from '$lib/components/OffCanvas.svelte';

	let showOffCanvas = false;
	let viewportWidth = 0;

	const handleResize = () => {
		if (typeof window === 'undefined') return;
		viewportWidth = window.innerWidth;
		if (viewportWidth > 1280) {
			showOffCanvas = true;
		} else {
			showOffCanvas = false;
		}
	};

	onMount(() => {
		if (typeof window === 'undefined') return;
		handleResize();
		window.addEventListener('resize', handleResize);
	});

	onDestroy(() => {
		if (typeof window === 'undefined') return;
		window.removeEventListener('resize', handleResize);
	});

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
		display: flex;
    align-items: center;
    justify-content: center;
	}

	.container {
		width: 100%;
		background-color: #221f26;
		border-radius: 1.3rem;
		height: 87.2rem;
		overflow: hidden;
    max-width: 1440px;
	}

	@media only screen and (min-width: 1280px) {
		.canvas-wrapper {
			position: inherit;
		}

		.container {
			display: flex;
      max-height: 66.4rem;
		}
	}
</style>
