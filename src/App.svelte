<script>
  import Card from "./Card.svelte";
  import Choice from "./Choice.svelte";
  import Button from "./Button.svelte";
  import ButtonBottom from "./ButtonBottom.svelte";
  import Surveybtn from "./Surveybtn.svelte";
  import Prog from "./Prog.svelte";

  import Icon from "svelte-awesome";
  import thLarge from "svelte-awesome/icons/thLarge";
  import font from "svelte-awesome/icons/font";
  import envelopeOpen from "svelte-awesome/icons/envelopeOpen";

  let showProg = true;
  let showChoice = false;
  let toggleText = false;
  let choiceColor;

  const handleClick = (color) => {
    choiceColor = color;
    showChoice = !showChoice;
  };

  const flipCards = () => {
    toggleText = !toggleText;
  };

  const showCard = () => {
    showProg = !showProg;
  };
</script>

<main>
  {#if showProg}
    <Surveybtn formLink={"https://forms.gle/FJzQ6ovsAoiZbPZM8"}
      ><Icon data={envelopeOpen} scale={1.2} /></Surveybtn
    >
    <Prog imgPath="/xian_by_one_vch.jpg" />
  {:else if showChoice}
    <Choice on:click={handleClick} {choiceColor} />
  {:else}
    <div class="btn-top">
      <Button {toggleText} on:click={flipCards}
        ><Icon data={font} scale={1.2} /></Button
      >
    </div>
    <div class="container">
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
    </div>
  {/if}
  <div class="btn-bottom">
    <ButtonBottom {showProg} on:click={showCard}
      ><Icon
        data={thLarge}
        scale={1.2}
        style="transform:rotate(90deg)"
      /></ButtonBottom
    >
  </div>
</main>

<style>
  main {
    text-align: center;
    padding: 1.2em;
    margin: auto;
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    align-items: center;
    height: 75vh;
  }
  .btn-top {
    position: fixed;
    top: 20px;
    right: 25px;
  }
  .btn-bottom {
    position: fixed;
    bottom: 15px;
    right: 25px;
  }
  .container {
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    align-items: center;
    flex: 1 1 auto;
    margin: auto;
  }
</style>
