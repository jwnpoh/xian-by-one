<script>
  import { fade } from "svelte/transition";
  export let showProg;
</script>

<div transition:fade={{ duration: 200 }}>
  <button class:on={showProg} class:off={!showProg} on:click><slot /></button>
</div>

<style>
  button {
    border: 0;
    display: flex;
    cursor: pointer;
    border-radius: 5px;
    padding: 5px 4px;
    font-weight: 900;
    box-shadow: 1px 1px 3px rgba(100, 100, 100, 0.3);
  }

  .on {
    background: rgb(200, 200, 200);
    color: rgb(153, 153, 153);
  }

  .off {
    background: rgba(40, 40, 40, 0.8);
    color: rgb(153, 153, 153);
  }
</style>
