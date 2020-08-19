<script>
	import * as nameBank from './data/name-bank.json'
	let name = "Generate a name Elon would approve of..."

	const getRandomValue = (array) => (
		array[Math.floor(Math.random() * array.length)]
	)

	const generateName = () => {
		name = `${getRandomValue(nameBank.mathSymbols).name} ${getRandomValue(nameBank.elvishSpellings).name} ${getRandomValue(nameBank.aircraft).name}`
	}
</script>

<main>
	<h1>Elon's Cradle</h1>
	<span>
		<p>{name}</p>
		<button on:click={generateName}>Generate Name</button>
	</span>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
		display: flex;
		justify-content: center;
    flex-wrap: wrap;
		height: 100vh;
		width: 100vw;
	}

	h1 {
		color: #89cff0;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
		width: 100%;
		height: fit-content;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>