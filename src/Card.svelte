<script>
  import { fade } from "svelte/transition";
  export let toggleText;
  export let text;
</script>

<div class:cardText={toggleText} class:card={!toggleText} on:click>
  {#if toggleText}
    <p class:hidden={!toggleText} transition:fade>{text}</p>
  {/if}
</div>

<style>
  .card,
  .cardText {
    display: flex;
    flex: 1 1 auto;
    position: relative;
    justify-content: space-evenly;
    align-items: center;
    width: 40%;
    height: 40%;
    box-sizing: border-box;
    padding: 10px;
    margin: 15px;
    border-radius: 10px;
  }

  .card {
    background-color: rgb(var(--boxColor));
    box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
    transition-duration: 500ms;
  }

  .cardText {
    background-color: rgba(var(--boxColor), 0.3);
    box-shadow: 0px 2px 4px rgba(100, 100, 100, 0.3);
    transition-duration: 500ms;
  }

  p {
    font-family: "CenturyGothic";
    font-weight: 900;
    font-size: 1.2em;
    color: rgb(245, 245, 245);
  }

  .hidden {
    display: none;
  }
</style>
