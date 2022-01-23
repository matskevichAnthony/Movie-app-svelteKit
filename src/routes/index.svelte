<script context="module">
	export async function load({ fetch }) {
		const res = await fetch(
			`  https://api.themoviedb.org/3/movie/popular?api_key=5baad519e3064eb2f2026518e5cf96b2&language=en-US&page=1`
		);
		const data = await res.json();
		if (res.ok) {
			return {
				props: { popular: data.results }
			};
		}
	}
</script>

<script>
	import PopularMovies from '../components/PopularMovies.svelte';
	import Search from '../components/Search.svelte';
	import { fly } from 'svelte/transition';
	export let popular;
</script>

<section in:fly={{ y: 50, duration: 400, delay: 400 }} out:fly={{ duration: 400 }}>
	<Search />
	<PopularMovies {popular} />
</section>
