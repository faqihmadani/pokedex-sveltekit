<script>
	export let pokeman;
</script>

<a
	href={`pokemon/${pokeman.id}`}
	class="bg-white p-6 text-gray-800 rounded-md shadow-sm hover:shadow-md flex flex-col items-center justify-center transition-shadow"
>
	<img class="h-[120px]" src={pokeman.image} alt={pokeman.name} />
	<h2 class="capitalize mt-3 text-2xl">{pokeman.id}. {pokeman.name}</h2>
</a>
