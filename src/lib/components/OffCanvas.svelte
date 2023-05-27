<script>
	import { createEventDispatcher } from 'svelte';

	import arrowLeft from '$lib/images/arrow-left.svg';

	const dispatch = createEventDispatcher();

	function toggleOffCanvas() {
		dispatch('toggleOffCanvas');
	}

	const links = ['home', 'my stats', 'members', 'settings', 'help'];
</script>

<nav>
	<button on:click={toggleOffCanvas} class="btn-wrapper">
		<img src={arrowLeft} alt="arrow-left" />
	</button>

	<div>
		<ul>
			{#each links as link}
				<li>{link}</li>
			{/each}
		</ul>
	</div>
</nav>

<style>
	button {
		border: none;
		background-color: transparent;
	}
	li {
		height: 4.3rem;
		padding-left: 4.3rem;
		color: white;
		font-weight: 400;
		font-size: 1.6rem;
		text-transform: uppercase;
		display: flex;
		align-items: center;
		cursor: pointer;
		transition: background-color 0.2s ease-in-out;
	}

	li:hover {
		font-weight: 700;
		background-color: #4497ff;
	}

	ul {
		list-style: none;
		margin-top: 3rem;
	}

	nav {
		display: flow-root;
		width: 21.3rem;
		background-color: #2c2931;
		min-height: 87.2rem;
	}

	.btn-wrapper {
		margin-left: 4.4rem;
		margin-top: 4.1rem;
		cursor: pointer;
	}

	@media only screen and (min-width: 1280px) {
		ul {
			margin-top: 5.8rem;
		}
		.btn-wrapper {
			display: none;
		}
	}
</style>
