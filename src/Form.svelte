<script>
  let word = '';

  const getSynonyms = async () => {
    await fetch(`https://www.dictionaryapi.com/api/v3/references/thesaurus/json/${word}?key=`)
      .then(res => res.json() )
      .then(data => console.log(data[0].meta.syns))
	}
</script>

<form>
  <input type="text" bind:value={word}>
  <button class="submit-btn" type="button" on:click={getSynonyms}>Submit</button>
</form>


<style>
  form {
	display: flex;
	margin: 0 auto;
	justify-content: center;
	flex-direction: column;
	width: 400px;
}

.submit-btn {
	border-radius: 50px;
	width: 175px;
	margin: 0 auto;
	background-color: #ff3e00;
	color: white;
	cursor: pointer;
}

.submit-btn:hover {
	border: 1px solid red
}
</style>