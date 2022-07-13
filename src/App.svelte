<script>
  import Card from "./Card.svelte";
  import Choice from "./Choice.svelte";
  import Button from "./Button.svelte";
  import Prog from "./Prog.svelte";

  let showProg = true;
  let showChoice = false;
  let choiceColor = "purple";
  let toggleText = false;

  function handleClick(color) {
    choiceColor = color;
    showChoice = !showChoice;
  }

  const flipCards = () => {
    toggleText = !toggleText;
  };

  const showCard = () => {
    showProg = !showProg;
  };
</script>

<main>
  <div class="btn-bottom">
    <Button toggleText={showProg} on:click={showCard}>Show programme</Button>
  </div>
  {#if showProg}
    <Prog imgPath="/Prog_v1-1_trial3.jpg" />
  {:else if showChoice}
    <Choice on:click={handleClick} {choiceColor} />
  {:else}
    <div class="btn-top">
      <Button {toggleText} on:click={flipCards}>🄰</Button>
    </div>
    <Card
      on:click={() => handleClick("red")}
      --boxColor="255,0,0"
      {toggleText}
      text="PASSION"
    />
    <Card
      on:click={() => handleClick("green")}
      --boxColor="0,255,0"
      {toggleText}
      text="FREEDOM"
    />
    <Card
      on:click={() => handleClick("blue")}
      --boxColor="0,0,255"
      {toggleText}
      text="SPIRITUALITY"
    />
    <Card
      on:click={() => handleClick("yellow")}
      --boxColor="255,255,0"
      {toggleText}
      text="NOSTALGIA"
    />
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
    align-content: stretch;
    height: 75vh;
  }
  .btn-top {
    position: fixed;
    top: 10px;
    right: 25px;
  }
  .btn-bottom {
    position: fixed;
    bottom: 15px;
    right: 25px;
  }
</style>
