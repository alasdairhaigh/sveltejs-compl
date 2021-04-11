<script>
	import ContactCard from './ContactCard.svelte';
	
	let name = 'Name';
	let jobTitle = 'Job title'
	let image = '';
	let description = 'A short description'
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
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello {uppercaseName}, my age is {age}!</h1>
<button on:click={incrementAge}>Change Age</button>
<p/>
Name: <input type="text" bind:value={name} />
Job Title: <input type="text" bind:value={jobTitle} />
Image: <input type="text" bind:value={image} />
<p />
Description: <textarea rows="3" bind:value={description} />


<ContactCard 
	userName={name} 
	{jobTitle} 
	{description} 
	userImage={image} 
/>
