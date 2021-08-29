<script>
  import Announcement from './components/Announcement.svelte';
  import Button from './components/Button.svelte';

  let firstName = '';
  let lastName = '';
  const src = 'favicon.png';

  // Loops
  let fruits = [
    { name: 'apple', color: 'red', amount: 4, id: 1 },
    { name: 'banana', color: 'yellow', amount: 2, id: 2 },
    { name: 'orange', color: 'orange', amount: 8, id: 3 },
  ];

  const deleteFruit = (id) => {
    fruits = fruits.filter((fruit) => fruit.id !== id);
  };

  let num = 7;

  // Reactive
  $: fullName = `${firstName} ${lastName}`;
  $: console.log(lastName);
</script>

<Announcement />

<main>
  <h1>Hello {fullName}</h1>
  <img {src} alt="Svelte" />

  <label for="firstName">First Name</label>
  <input type="text" bind:value={firstName} />
  <label for="lastName">Last Name</label>
  <input type="text" bind:value={lastName} />

  {#each fruits as fruit (fruit.id)}
    {#if fruit.amount > 4}
      <div class="card">
        <h4>{fruit.name}</h4>
        <p>{fruit.color}</p>
        <button on:click={() => deleteFruit(fruit.id)}>Delete</button>
      </div>
    {:else}
      <p>The amount of {fruit.name} is less than or equal to 4</p>
    {/if}
  {:else}
    <p>There is no fruit</p>
  {/each}

  <Button btnText={'Hello World'} />
  <Button />
</main>

<style>
  main {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
  }
  img {
    height: 50px;
  }
  h1 {
    text-align: center;
  }
  h4,
  p {
    margin: 4px 0;
  }
  .card {
    margin-bottom: 2px;
    padding: 10px;
    border: 1px solid rgba(0, 0, 0, 0.2);
    width: 400px;
  }
</style>
