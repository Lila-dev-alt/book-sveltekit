<script>
	import TagSelector from '../../lib/components/Tag.svelte';
	import { theCats } from '$lib/data/Cats.js';
	import { dataset_dev } from 'svelte/internal';

	let currentTags = [];
	const tags = ['grooming', 'intelligence'];
	$: displayedTags = tags.filter((t) => !currentTags.includes(t));

	function addTag(event) {
		// update currentTags
		currentTags = [...currentTags, event.detail];
	}
</script>

{#if currentTags}
	{#each currentTags as tag}
		<div>
			{tag}
		</div>
		{#each $theCats as data}
			{#if tag === 'gooming'}
				<p>Name : {data.name}</p>
				<p>Grooming : {data.grooming}</p>
			{:else}
				<p>Name : {data.name}</p>
				<p>Inteligence: {data.intelligence}</p>
			{/if}
		{/each}
	{:else}{/each}
{/if}

<TagSelector tags={displayedTags} on:select={addTag} />
