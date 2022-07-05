<script>
  import Card from "./Card.svelte";
  import Choice from "./Choice.svelte";

  let showChoice = false;
  let choiceColor = "purple";

  function handleClick(color) {
    choiceColor = color;
    showChoice = !showChoice;
  }
</script>

<main>
  {#if showChoice}
    <Choice on:click={handleClick} {choiceColor} />
  {:else}
    <Card on:click={() => handleClick("red")} boxColor="red" />
    <Card on:click={() => handleClick("green")} boxColor="green" />
    <Card on:click={() => handleClick("blue")} boxColor="blue" />
    <Card on:click={() => handleClick("yellow")} boxColor="yellow" />
  {/if}
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    margin: auto;
    display: flex;
    flex-flow: row wrap;
    justify-content: space-evenly;
    align-items: center;
    height: 75vh;
  }
</style>
