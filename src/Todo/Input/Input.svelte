<script>
	import { createEventDispatcher } from 'svelte';

  export let task = '';
  export let adds;

  const dispatch = createEventDispatcher();

  const add = () => dispatch('submit');
  const remove = () => dispatch('remove', task);
</script>

<style lang="scss">

.add-btn {
  background-color: lightgreen;
  color: white;
}

.remove-btn {
  background-color: crimson;
  color: white;
  padding-right: 0.6em;
  padding-left: 0.6em;
}

</style>

<div>

  {#if adds}
    <input type="text" bind:value={task}>
    <button on:click={add} disabled={!task} class="add-btn">+</button>
    {:else}
    <input type="text" bind:value={task} disabled>
    <button on:click={remove} class="remove-btn">-</button>
  {/if}

</div>