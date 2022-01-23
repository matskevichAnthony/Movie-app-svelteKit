<script>
	import global from '../global.css';
	import Nav from '../components/Nav.svelte';
</script>

<svelte:head>
	<title>Movies App</title>
</svelte:head>

<Nav />
<!-- // inside slot the pages will be rendered -->
<slot />
