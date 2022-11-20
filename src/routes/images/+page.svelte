<script>
	import Image from '../../lib/components/Image.svelte';
	import { cats } from '../../lib/data/Cats.js';
	const images = $cats.flatMap((data) => data.image?.url);
</script>

<svelte:head>
	<title>Images</title>
	<meta name="description" content="Images" />
</svelte:head>

<div class="text-column">
	<Image {images} />
</div>
