<script>
  import { fade } from "svelte/transition";
  export let formLink;
</script>

<div transition:fade={{ duration: 100 }}>
  <a href={formLink} target="_blank"><button><slot /></button></a>
</div>

<style>
  button {
    position: fixed;
    top: 25px;
    right: 25px;
    border: 0;
    display: flex;
    cursor: pointer;
    border-radius: 5px;
    padding: 5px 4px;
    font-weight: 900;
    font-size: 1.1em;
    box-shadow: 1px 1px 3px rgba(100, 100, 100, 0.3);
    background: rgb(200, 200, 200);
    color: rgb(153, 153, 153);
  }
</style>
