<script>
	import About from './components/About.svelte';
	import Text from './components/Text.svelte';
	import Person from './components/Person.svelte';
	import Skills from './components/Skills.svelte';
	export let name;
	export let lastName;
	let sveleteLogo = 'https://arepa.s3.amazonaws.com/svelte-logo.png'

	const data = {
		name: 'Julian',
		lastName: 'Gil',
		age: '30',
	}
</script>

<style>

	/* Globla styles */
	:global(body) {
		background-color: #f2eee2;
		color: #0084f6;
	}

	/* Applying variables */
	:global(:root) {
		--theme-light: #f2eee2;
		--theme-dark: #121212;
		--primary: #4bb2f9;
		--secondary: #007c89;
	}

	/* Applying darkMode */
	:global(body.dark-mode) {
		background-color: #121212;
		color: #bfc2c7;
	}

	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	main img {
		width: 30%;
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

<main>
	<h1>Hello {name} {lastName}!</h1>
	<About />
	<Text anotherText={'hola'}/>
	<Text />
	<Person {...data} />
	<Skills />
	<img src={sveleteLogo} alt='Svelte' />
</main>