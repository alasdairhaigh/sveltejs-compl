<script>
	let name = 'Max';
	let age = 30;

	$: uppercaseName = name.toUpperCase();

	$: console.log(name);

	$: if (name === 'Alasdair') {
		console.log('It runs!');
		age = 37;
	}

	function incrementAge() {
		age += 1;
	}

	function changeName() {
		name = 'Alasdair';
	}
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello {uppercaseName}, my age is {age}!</h1>
<button on:click={incrementAge}>Change Age</button>
<button on:click={changeName}>Change name</button>
