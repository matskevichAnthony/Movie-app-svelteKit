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
	export let popular;
</script>

<section>
	<Search />
	<PopularMovies {popular} />
</section>
