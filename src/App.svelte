
<script>
	/*importacion de componentes*/
	import About from './components/About.svelte';
	import Text from './components/Text.svelte';
	import Person from './components/Person.svelte'
	import Skills from './components/Skills.svelte';
	import Input from './components/Input.svelte';
	import Photos from './components/Photos.svelte';
	import ButtonCount from './components/ButtonCount.svelte';


	/*propiedades*/
	export let name;
	export let lastname;
	/*declaracion de variables*/
	let svelteLogo = "https://arepa.s3.amazonaws.com/svelte-logo.png";

	const data = {
		name: 'Gabriel',
		lastname: 'Gomez',
		age: 50
		
		}

</script>

<style>
	/*estilos globales */
	:global(body){
		background-color : #f2eee2;
		color: #0084f5;
	}
	/*variables globales*/
	:global(:root){
		--theme-color: purple;

	}
	:global(body.dark-mode){

		background-color: #1d3040;
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
	<h1>{name} {lastname}!</h1>
	<About />
	<Text anotherText="Hola!" />
	<Text />
	<!--usando operador de propagación-->
	<Person {...data} />
	<!--usando un each sencillo-->
	<Skills />
	<Input />
	<ButtonCount />
	<Photos />
	<img src={svelteLogo} alt="Svelte">
</main>
