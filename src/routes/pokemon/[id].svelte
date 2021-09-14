<script context="module">
	export async function load({ page }) {
		const id = page.params.id;
		const url = `https://pokeapi.co/api/v2/pokemon/${id}`;
		const res = await fetch(url);
		const pokeman = await res.json();
		return { props: { pokeman } };
	}
</script>

<script>
	export let pokeman;
	const type = pokeman.types[0].type.name;
	const hp = pokeman.stats[0].base_stat;
	const attack = pokeman.stats[1].base_stat;
	const defense = pokeman.stats[2].base_stat;
	const speed = pokeman.stats[5].base_stat;
</script>

<div class="bg-white py-5 px-4 flex items-center flex-col">
	<h1 class="text-2xl uppercase font-medium text-center">{pokeman.name}</h1>
	<img class="my-8" src={pokeman.sprites.other.dream_world.front_default} alt={pokeman.name} />
	<h1>
		HP : <strong>{hp}</strong> | Attack :
		<strong>{attack} </strong>| Defense : <strong>{defense}</strong> | Speed :
		<strong>{speed}</strong>
	</h1>
	<h1 class="capitalize">Type : <strong>{type}</strong></h1>
	<h1>Weight : <strong>{pokeman.weight}</strong></h1>
	<h1>Height : <strong>{pokeman.height}</strong></h1>
</div>
