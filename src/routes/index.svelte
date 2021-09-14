<script>
	import { pokemon } from '../stores/PokeStore';
	import PokemanCard from '../components/PokemanCard.svelte';

	let searchTerm = '';
	let filteredPokemon = [];

	$: {
		if (searchTerm) {
			//Cari pokemon
			filteredPokemon = $pokemon.filter((pokeman) =>
				pokeman.name.toLowerCase().includes(searchTerm.toLowerCase())
			);
		} else {
			filteredPokemon = [...$pokemon];
		}
	}
</script>

<svelte:head>
	<title>Pokedex</title>
</svelte:head>

<h1 class="text-6xl text-center mt-4 mb-8 uppercase font-semibold">Pokedex</h1>
<input
	class=" w-full rounded-sm py-2 px-4 text-lg border-2 border-gray-200"
	placeholder="Search Pokemon"
	type="text"
	bind:value={searchTerm}
/>

<div class="grid gap-4 lg:grid-cols-3 md:grid-cols-2 grid-cols-1 py-4">
	{#each filteredPokemon as pokeman}
		<PokemanCard {pokeman} />
	{/each}
</div>
