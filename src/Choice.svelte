<script>
  import { fade } from "svelte/transition";
  export let choiceColor;
</script>

<div
  transition:fade
  class="choiceCard"
  style="background-color: {choiceColor};"
  on:click
/>

<style>
  .choiceCard {
    width: 100%;
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
  }
</style>
