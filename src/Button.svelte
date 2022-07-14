<script>
  export let toggleText;
  export let showProg;
</script>

{#if showProg}
  <button class:on={showProg} class:off={!showProg} on:click><slot /></button>
{:else}
  <button class:text-on={toggleText} class:text-off={!toggleText} on:click
    ><slot /></button
  >
{/if}

<style>
  button {
    border: 0;
    display: flex;
    cursor: pointer;
    border-radius: 5px;
    padding: 4px 4px;
    font-weight: 900;
    font-size: 1.1em;
    color: rgb(150, 150, 150);
    box-shadow: 1px 2px 3px rgba(100, 100, 100, 0.3);
  }

  .on {
    background: rgb(200, 200, 200);
    color: rgb(100, 100, 100);
  }

  .off {
    background: rgba(50, 50, 50, 0.8);
    color: white;
  }
  .text-on {
    background: rgba(50, 50, 50, 0.8);
    color: white;
  }
  .text-off {
    background: rgba(40, 40, 40, 0.8);
    color: rgb(200, 200, 200);
  }
</style>
