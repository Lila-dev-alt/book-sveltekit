<script>
	// @ts-nocheck

	import { dataset_dev } from 'svelte/internal';
	export let img;
	export let name;
	export let race;
	export let age;
</script>

<div class="miniProfile">
	<h2 class="title">My profile</h2>
	<div class="container">
		<div>
			<img src={img} alt="cat" />
		</div>
		<div class="text-container">
			<div class="hello">
				<p>Name:</p>
				<p>{name}</p>
			</div>
			<div class="hello">
				<p>Breed:</p>
				<p>{race}</p>
			</div>
			<div class="hello">
				<p>Age:</p>
				<p>{age}</p>
			</div>
		</div>
	</div>
</div>

<style>
	.title {
		text-align: right;
		font-weight: 700;
		font-size: 30px;
		color: blue;
	}
	img {
		max-width: 300px;
	}
	.container {
		display: flex;
		justify-content: end;
		align-items: center;
	}
	.text-container {
		margin-left: 2%;
	}

	.text-container .hello {
		display: flex;
		justify-content: space-around;
	}
</style>
