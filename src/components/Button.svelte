<script>
  // export variable for other components to use
  export let btnText = 'Default Text';
</script>

<div on:click>
  <span>Click to log</span>
  <button>{btnText}</button>
</div>

<style>
  div {
    padding: 1rem;
    border: 1px solid #666;
  }
  button {
    background-color: pink;
  }
</style>
