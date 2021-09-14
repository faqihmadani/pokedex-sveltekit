<script>
	import Nav from '../components/Nav.svelte';
	import Footer from '../components/Footer.svelte';
</script>

<div class="container-lg mx-auto px-6 min-h-screen bg-[#c5ecc9]">
	<Nav />
	<slot />
	<Footer />
</div>

<style>
	@tailwind base;
	@tailwind components;
	@tailwind utilities;
</style>
