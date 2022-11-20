<script>
	import MiniProfile from '$lib/components/miniProfile.svelte';

	const dataProfile = {
		img: 'https://www.zooplus.fr/magazine/wp-content/uploads/2019/08/chat-siberien-sur-un-lit.jpg',
		name: 'Mochi',
		race: 'Siberian',
		age: '2 month'
	};
</script>

<svelte:head>
	<title>My profile</title>
	<meta name="description" content="About my profile" />
</svelte:head>

<div class="text-column">
	<MiniProfile {...dataProfile} />
</div>
