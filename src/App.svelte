<script>
	let firstName = 'John';
	let lastName = 'Doe';
	let beltColor = 'black';

	// Reactive value
	$: fullname = `${firstName} ${lastName}`;
	$: {
		console.log(fullname);
		console.log(beltColor);
	}

	const handleClick = () => {
		if(beltColor === 'black') {
			beltColor = 'green';
		} else {
			beltColor = 'black';
		}
	}

	const handleInput = (e) => {
		beltColor = e.target.value;
	}
</script>

<main>
	<h1>Hello {fullname}!</h1>
	<p><span>{beltColor}</span> belt.</p>

	<button on:click={handleClick}>Change belt color.</button>
	<!-- <div style="margin-top: 1em;">
		<div>One-way data binding.</div>
		<input type="text" on:input={handleInput}>
	</div> -->
	<div>
		<input type="text" bind:value={firstName}>
		<input type="text" bind:value={lastName}>
		<input type="text" bind:value={beltColor}>
	</div>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>