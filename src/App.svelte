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
	<span class="interaction-container">
		<p id="name">{name}</p>
		<button on:click={generateName}>Generate Name</button>
	</span>
</main>

<style>
	main {
		text-align: center;
		max-width: 240px;
		margin: 0 auto;
		height: 75%;
		width: 100%;
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

	.interaction-container {
		height: 100%;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
	}

	#name {
		width: 100%;
    font-size: 1.5em;
    color: #89cfef;
	}
</style>