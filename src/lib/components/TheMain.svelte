<script>
	import { createEventDispatcher } from 'svelte';

	import hamburger from '$lib/images/hamburger.svg';
	import BaseButton from '$lib/components/BaseButton.svelte';

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
			<a class="logo" href="/">LOGO</a>
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
		height: 100%;
		width: 100%;
		background: bottom left -15rem / cover no-repeat url('/src/lib/images/bg-main.jpg') #221f26;
		background-blend-mode: screen, normal;
	}

	.logo {
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

	@media only screen and (min-width: 1280px) {
		main {
			background-position: center right;
		}

		.hamburger-wrapper {
			display: none;
		}

		header {
			margin-top: 5.8rem;
			margin-left: 10.3rem;
		}

		h1 {
			margin-top: 4.6rem;
			margin-left: 10.1rem;
			font-size: 6.4rem;
			line-height: 5.696rem;
		}

		h2 {
			margin-top: 3.3rem;
			margin-left: 10.2rem;
			font-size: 4.8rem;
			line-height: 5.347rem;
			max-width: 39.8rem;
		}

		.btn-wrapper {
			margin-left: 10.2rem;
			margin-top: 5.7rem;
		}
	}
</style>
