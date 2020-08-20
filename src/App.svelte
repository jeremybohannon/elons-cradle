<script>
	import * as nameBank from './data/name-bank.json'
	import * as messages from './data/messages.json'
	let name = ""
	let compliment = ""
	let pronunciation = ""

	const getRandomValue = (array) => (
		array[Math.floor(Math.random() * array.length)]
	)

	const generateName = () => {
		let mathSymbol = getRandomValue(nameBank.mathSymbols)
		let elvishSpelling = getRandomValue(nameBank.elvishSpellings)
		let aircraft = getRandomValue(nameBank.aircraft)

		name = `${mathSymbol.name} ${elvishSpelling.name} ${aircraft.name}`
		pronunciation = `Pronounced '${mathSymbol.pronunciation} ${elvishSpelling.pronunciation} ${aircraft.pronunciation}'`
		
		compliment = getRandomValue(messages.compliment)
	}
	
	const callToAction = getRandomValue(messages.callToAction)
</script>

<main>
	<h1>Elon's Cradle</h1>
	<span>
		<h2>{callToAction}</h2><span>Click below to get your name!</span>
	</span>
	<div class="interaction-container">
		<span class="w100"><p id="name">{name}</p></span>
		<span class="w100"><p>{pronunciation}</p></span>
		<span class="w100"><p>{compliment}</p>	</span>
	</div>
	<div>
		<button on:click={generateName}>Generate Name</button>
	</div>
</main>

<style>
	main {
		text-align: center;
		max-width: 240px;
		margin: 0 auto;
		height: 100%;
		width: 100%;
	}

	h1 {
		color: #89cff0;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
		width: 100%;
		height: fit-content;
		margin: 0;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}

	.interaction-container {
		height: 50%;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
	}

	#name {
    font-size: 3em;
    color: #89cfef;
	}

	.w100 {
		width: 100%;
	}
</style>