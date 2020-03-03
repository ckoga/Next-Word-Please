<script>
  import { createEventDispatcher } from 'svelte';
  const dispatch = createEventDispatcher();

  export let data;
  const clickHandler = () => {
    dispatch('message', {
      text: data
    })
  }
</script>

<button class='synonyms' type="button" on:click={clickHandler}>{data}</button>

<style>
  .synonyms {
	border-radius: 50px;
	background-color: #ff3e00;
	color: white;
  cursor: pointer;
  margin: 7px;
  padding: 10px;
}
</style>