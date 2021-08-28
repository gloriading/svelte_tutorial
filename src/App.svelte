<script>
  const name = 'Gloria';
  const src = 'favicon.png';
  let count = 0;

  const increment = () => (count += 1);
</script>

<main>
  <h1>Hello {name}</h1>
  <h3>Counter: {count}</h3>
  <button on:click={increment}>Add 1 to counter</button>
  <img {src} alt="Svelte" />
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
