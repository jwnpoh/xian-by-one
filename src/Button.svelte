<script>
  export let toggleText;
</script>

<button class:on={toggleText} class:off={!toggleText} on:click><slot /></button>

<style>
  button {
    border: 0;
    cursor: pointer;
    border-radius: 6px;
    padding: 1px 4px;
    font-weight: 900;
    font-size: 1.1em;
    color: rgb(150, 150, 150);
    box-shadow: 1px 2px 3px rgba(100, 100, 100, 0.3);
  }

  .on {
    background: rgb(180, 180, 180);
    color: black;
  }

  .off {
    background: rgba(50, 50, 50, 0.8);
    color: white;
  }
</style>
