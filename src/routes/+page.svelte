<script>
	import Counter from '../components/Counter.svelte';
	import welcome from '$lib/images/svelte-welcome.webp';
	import welcome_fallback from '$lib/images/svelte-welcome.png';
	import MyComp from '../components/MyComp.svelte';
	import TailCard from '../components/TailCard.svelte';
</script>

<svelte:head>
	<title>Svelte baby app</title>
	<meta name="description" content="Svelte baby app" />
</svelte:head>

<section>

	<Counter />
	<MyComp myString={'Passed from prop'} myValue={120}/>
	<TailCard />
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}

	h1 {
		width: 100%;
	}

	.welcome {
		display: block;
		position: relative;
		width: 100%;
		height: 0;
		padding: 0 0 calc(100% * 495 / 2048) 0;
	}

	.welcome img {
		position: absolute;
		width: 100%;
		height: 100%;
		top: 0;
		display: block;
	}
</style>
