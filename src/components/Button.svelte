<script>
  // export variable for other components to use
  export let btnText = 'Default Text';
</script>

<!-- <div on:click|self> -->
<div>
  <button on:click|once>{btnText}</button>
</div>

<style>
  div {
    padding: 1rem;
    border: 2px solid #666;
  }
  button {
    background-color: pink;
  }
</style>
