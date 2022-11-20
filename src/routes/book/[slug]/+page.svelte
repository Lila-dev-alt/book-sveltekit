<script>
	import Cat from '$lib/components/Cat.svelte';
	import { cats } from '$lib/data/Cats.js';
	import { page } from '$app/stores';

	$: data = $cats.find((data) => data.name === $page.params.slug);
</script>

<svelte:head>
	<title>Book</title>
	<meta name="description" content="Book" />
</svelte:head>

<main>
	<Cat name={data.name} description={data.description} origin={data.origin} image={data.image} />
</main>
