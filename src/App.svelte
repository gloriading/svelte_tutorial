<script>
  let name = '';
  const src = 'favicon.png';
  let count = 0;
  const increment = () => (count += 1);

  // const handleInput = (event) => {
  //   name = event.target.value;
  // };

  const resetName = () => (name = 'unknown');
</script>

<main>
  <h1>Hello {name}</h1>
  <h3>Counter: {count}</h3>
  <button on:click={increment}>Add 1 to counter</button>
  <img {src} alt="Svelte" />
  <input type="text" bind:value={name} />
  <!-- <input type="text" on:input={handleInput} value={name} /> -->
  <button on:click={resetName}>Set name to unknown</button>
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
</style>
