<script>
	import arrowRight from '$lib/images/arrow-right.svg';

	export let label = 'Click me';
</script>

<button>
	<img src={arrowRight} alt="Arrow right" />
	{label}
</button>

<style>
	button {
		text-transform: uppercase;
		width: 22.3rem;
		height: 6rem;
		border: 0.1rem solid #4d4d4d;
		background-color: transparent;
		color: white;
		font-size: 1.8rem;
		font-weight: 700;
		line-height: 2rem;
		display: flex;
		align-items: center;
		gap: 1.6rem;
    padding-inline: 1.1rem;
	}
</style>
