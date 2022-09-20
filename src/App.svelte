<script>
	let people = [
		{ name: 'jose', beltColor: 'black', age: 24, id: 1},
		{ name: 'andrei', beltColor: 'green', age: 20, id: 2},
		{ name: 'micah', beltColor: 'white', age: 17, id: 3},
	];

	const handleClick = (id) => {
		people = people.filter((person) => person.id != id);
	}
</script>

<main>
	<ul>
		{#each people as {id, name, beltColor} (id)}
			<li>
				{id}. {name} - {beltColor}
				<button on:click={() => handleClick(id)}>Delete</button>
			</li>
		{:else}
			<li>no people to show...</li>
		{/each}
	</ul>
</main>

<style>
	main {
		text-align: justify;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>