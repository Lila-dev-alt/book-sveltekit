<script>
	let name;
	let description;
	let origin;
	export let addToArray = (data) => {};
</script>

<h2>Add of cat breed in the book</h2>
<input bind:value={name} type="text" placeholder="breed name" />
<input bind:value={description} type="text" placeholder="breed description" />
<input bind:value={origin} type="text" placeholder="breed origin" />
<button
	on:click={() => {
		addToArray({ name, description, origin });
	}}
	>Add cat breed
</button>

<style>
	input[type='text'] {
		width: 100%;
		padding: 12px 20px;
		margin: 8px 0;
		box-sizing: border-box;
		border: 2px solid purple;
		border-radius: 10px;
	}
	input[type='text']:focus {
		background-color: lightblue;
		border: 3px solid #555;
	}
	button {
		background-color: purple;
		border: none;
		color: white;
		padding: 16px 32px;
		text-decoration: none;
		margin: 4px 2px;
		cursor: pointer;
	}
</style>
