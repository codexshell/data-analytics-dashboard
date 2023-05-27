<script>
	import arrowLeft from '$lib/images/arrow-left.svg';

	const links = ['home', 'my stats', 'members', 'settings', 'help'];
</script>

<nav>
	<div class="img-wrapper">
		<img src={arrowLeft} alt="arrow-left" />
	</div>

	<div>
		<ul>
			{#each links as link}
				<li>{link}</li>
			{/each}
		</ul>
	</div>
</nav>

<style>
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
	}

	.img-wrapper {
		margin-left: 4.4rem;
		margin-top: 4.1rem;
		cursor: pointer;
	}
</style>
