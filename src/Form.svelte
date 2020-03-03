<script>
  import { createEventDispatcher } from 'svelte';
  const dispatch = createEventDispatcher();

  let word = '';

  const clickHandler = () => {
    dispatch('message', {
      text: word
    })
  }
</script>

<form>
  <input type="text" bind:value={word}>
  <button class="submit-btn" type="button" on:click={clickHandler}>Submit</button>
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