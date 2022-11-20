<script>
	import Image from '$lib/components/Image.svelte';
	import { cats } from '$lib/data/Cats.js';
	import Cat from '$lib/components/Cat.svelte';
	import Search from '$lib/components/Search.svelte';
	import NotFound from '$lib/components/NotFound.svelte';
	import AddCat from '$lib/components/AddCat.svelte';
	let searchTerm = '';
	let filteredCats = [];

	const searchCats = () => {
		return (filteredCats = $cats.filter((cat) => {
			let catName = cat.name.toLowerCase();
			return catName.includes(searchTerm.toLowerCase());
		}));
	};
	function addToArray({ name, description, origin }) {
		console.log('name', name);
		$cats = [
			...$cats,
			{
				description,
				image: {
					id: '1',
					height: 1,
					width: 1,
					url: 'https://www.zooplus.fr/magazine/wp-content/uploads/2019/08/chat-siberien-sur-un-lit.jpg'
				},
				name,
				origin
			}
		];
	}
</script>

<svelte:head>
	<title>Book</title>
	<meta name="description" content="Images" />
</svelte:head>

<main>
	<h1 class="bold">🐱 Cat BOOK🐱</h1>
	<div class="search-input">
		<Search bind:searchTerm on:input={searchCats} />
	</div>

	{#if searchTerm && filteredCats.length === 0}
		<NotFound />
	{:else if filteredCats.length > 0}
		{#each filteredCats as data}
			<div class="container-only-cat">
				<div class="contain">
					<a href={`/book/${data.name}`}>{data.name}</a>
					<Cat
						name={data.name}
						description={data.description}
						origin={data.origin}
						image={data.image}
					/>
				</div>
			</div>
		{/each}
	{:else}
		<div class="container">
			{#each $cats as data}
				<div class="contain">
					<a href={`/book/${data.name}`}>{data.name}</a>
					<Cat
						name={data.name}
						description={data.description}
						origin={data.origin}
						image={data.image}
					/>
				</div>
			{/each}
		</div>
		<AddCat {addToArray} />
	{/if}
</main>

<style>
	.bold {
		font-weight: 600;
		font-weight: 30px;
	}
	.container {
		display: flex;
		justify-content: center;
		flex-wrap: wrap;
	}
	.container-only-cat {
		display: flex;
		justify-content: flex-end;
		flex-wrap: wrap;
	}
	.search-input {
		width: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
		padding: 2% 0;
	}
	.contain {
		display: flex;
		flex-direction: column;
		align-items: center;
	}
</style>
