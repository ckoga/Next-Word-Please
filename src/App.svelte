<script>
	import 
	import Form from './Form.svelte';
	import Button from './Button.svelte';

	let synonyms = [];

	const getSynonyms = async (event) => {
    await fetch(`https://www.dictionaryapi.com/api/v3/references/thesaurus/json/${event.detail.text}?key=API_KEY`)
      .then(res => res.json())
      .then(data => synonyms = data[0].meta.syns)
      .catch(err => console.log(err))
	}
</script>

<main>
	<p>Struggling with a word?</p>
	<h1>Next Word Please!</h1>
	<p>Give us one</p>
	<Form on:message={getSynonyms}/>
	<p>We'll give you a few:</p>
	<section class="button-container">
		<Button data={synonyms}/>
	</section>
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
		font-weight: bold;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>