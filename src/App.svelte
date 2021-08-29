<script>
  let firstName = '';
  let lastName = '';

  const src = 'favicon.png';

  // Loops
  let fruits = [
    { name: 'apple', color: 'red', id: 1 },
    { name: 'banana', color: 'yellow', id: 2 },
    { name: 'orange', color: 'orange', id: 3 },
  ];

  // Reactive
  $: fullName = `${firstName} ${lastName}`;
  $: console.log(lastName);
</script>

<main>
  <h1>Hello {fullName}</h1>
  <img {src} alt="Svelte" />

  <label for="firstName">First Name</label>
  <input type="text" bind:value={firstName} />
  <label for="lastName">Last Name</label>
  <input type="text" bind:value={lastName} />

  {#each fruits as fruit (fruit.id)}
    <div class="card">
      <h4>{fruit.name}</h4>
      <p>{fruit.color}</p>
    </div>
  {:else}
    <p>There is no fruit</p>
  {/each}
</main>

<style>
  main {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
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
