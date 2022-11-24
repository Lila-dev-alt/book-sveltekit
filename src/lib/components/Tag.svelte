<script>
	import { slide } from 'svelte/transition';
	import { createEventDispatcher } from 'svelte';
	const dispatch = createEventDispatcher();

	export let tags;

	let open = false;
	function select(t) {
		dispatch('select', t);
		open = false;
	}
</script>

<button on:click={() => (open = !open)}> + </button>

{#if open}
	<ul transition:slide>
		{#each tags as tag}
			<li>
				<button on:click={() => select(tag)}>
					{tag}
				</button>
			</li>
		{/each}
	</ul>
{/if}

<style>
	ul {
		padding: 0;
		list-style: none;
	}
	li {
		padding: 0.5rem;
		width: fit-content;
		border: 1px solid black;
	}
</style>
