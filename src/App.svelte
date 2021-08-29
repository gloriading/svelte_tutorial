<script>
  import Announcement from './components/Announcement.svelte';
  import Button from './components/Button.svelte';
  import Card from './components/Card.svelte';

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

  // Reactive
  $: fullName = `${firstName} ${lastName}`;
  $: console.log(lastName);

  const log = () => {
    console.log('element clicked!');
  };

  // input types
  let name;
  let num;
  let isChecked = false;
  let value = 1;
  let selected;
  let questions = [
    { id: 1, text: 'your favorite color?' },
    { id: 2, text: 'your favorite fruit?' },
  ];
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

  <button on:click={log}>App button</button>
  <Button on:click={log} btnText={'Hello World'} />
  <Card>
    <div>
      <h3>Card</h3>
      <p>this is a card</p>
    </div>
    <button slot="button">Card Button</button>
    <div>
      <h4>Footer</h4>
    </div>
  </Card>

  <div class="inputTypes">
    <input type="text" bind:value={name} />
    <input type="number" bind:value={num} />
    <input type="checkbox" bind:value={isChecked} />

    <label>
      <input type="radio" value={1} bind:group={value} />
      1
    </label>
    <label>
      <input type="radio" value={2} bind:group={value} />
      2
    </label>
    <label>
      <input type="radio" value={3} bind:group={value} />
      3
    </label>

    <select bind:value={selected}>
      {#each questions as question (question.id)}
        <option value={question}>
          {question.text}
        </option>
      {/each}
    </select>
  </div>
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
  .inputTypes {
    width: 400px;
    padding: 10px;

    margin: 10px 0;
    border: 2px solid yellowgreen;
    display: flex;
    flex-direction: column;
  }
</style>
