<script>
import Input from './Input/Input';

let newTask;

let removingElement = false;

let addingElement = true;

let tasks = [];

const handleSubmit = () => {
  tasks = [...tasks, newTask];
}

const handleRemove = (task) => {
  tasks = tasks.filter(t => t !== task.detail);
}

</script>

<style lang="scss">
  /* your styles go here */
</style>

<div>

<h2>TODO Svelte App</h2>

{#each tasks as task}
  <Input bind:task={task} bind:adds={removingElement} on:remove={handleRemove} />
{/each}

<Input bind:task={newTask} bind:adds={addingElement} on:submit={handleSubmit}/>

</div>