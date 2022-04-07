<script context="module">
	export async function load({ fetch }) {
		const res = await fetch('https://dog-facts-api.herokuapp.com/api/v1/resources/dogs?number=1');
		const data = await res.json();
		if (res.ok) {
			return {
				props: { fact: data[0] }
			};
		}
	}
</script>

<script>
	import Facts from '../components/Facts.svelte';
	export let fact;
</script>

<body>
	<section>
		<Facts {fact} />
	</section>
</body>

<style>
	*,
	*::after,
	*::before {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
	}

	body {
		height: 100vh;
		display: flex;
		justify-content: center;
		align-items: center;
		text-align: center;
		font-family: Arial;
	}
</style>
