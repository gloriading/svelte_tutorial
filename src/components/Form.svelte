<script>
  import { createEventDispatcher } from 'svelte';
  const dispatch = createEventDispatcher();

  let name;
  let color;
  const handleSubmit = () => {
    const food = {
      name,
      color,
      id: Math.random(),
    };

    dispatch('addFood', food);
    name = '';
    color = '';
  };
</script>

<form on:submit|preventDefault={handleSubmit}>
  <input type="text" placeholder="name" bind:value={name} />
  <input type="text" placeholder="color" bind:value={color} />
  <button>Add Food</button>
</form>

<style></style>
