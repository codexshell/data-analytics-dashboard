<script>
	import { createEventDispatcher } from 'svelte';

	import hamburger from '$lib/images/hamburger.svg';
	import BaseButton from './BaseButton.svelte';

	const dispatch = createEventDispatcher();

	function toggleOffCanvas() {
		dispatch('toggleOffCanvas');
	}
</script>

<main>
	<header>
		<button on:click={toggleOffCanvas} class="hamburger-wrapper">
			<img src={hamburger} alt="hamburger" />
		</button>
		<span>
			<a href="/">LOGO</a>
		</span>
	</header>

	<h1>
		Data<br />
		Analytics
	</h1>

	<h2>Making sense of your traffic.</h2>

	<div class="btn-wrapper">
		<BaseButton label="Go to my stats" />
	</div>
</main>

<style>
	button {
		background-color: transparent;
		border: none;
	}
	.hamburger-wrapper {
		cursor: pointer;
	}

	.btn-wrapper {
		margin-left: 4.2rem;
		margin-top: 4.6rem;
	}

	h2 {
		font-weight: 200;
		font-size: 34px;
		color: #847d93;
		margin-left: 4.2rem;
		margin-top: 3.7rem;
	}

	h1 {
		font-weight: 800;
		font-size: 4.8rem;
		line-height: 4.272rem;
		margin-left: 4.2rem;
		color: #fff;
		margin-top: 23.9rem;
		text-transform: uppercase;
	}

	main {
		display: flow-root;
	}

	a {
		text-decoration: none;
		color: #2d7dff;
		font-weight: 800;
		font-size: 2.4rem;
		line-height: 2.674rem;
		letter-spacing: -0.12em;
	}

	header {
		display: flex;
		align-items: center;
		gap: 10.8rem;
		margin-inline: 3.2rem;
		margin-block: 2.4rem;
	}
</style>
