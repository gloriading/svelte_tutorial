<script>
  let firstName = '';
  let lastName = '';

  const src = 'favicon.png';

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
