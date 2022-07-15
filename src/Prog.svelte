<script>
  import { onMount, onDestroy } from "svelte";
  import { fade } from "svelte/transition";
  import { sineOut } from "svelte/easing";

  export let imgPath;
  let scroll;

  onMount(() => {
    scroll = localStorage.getItem("scroll");
    scrollTo(0, scroll);
  });

  onDestroy(() => {
    localStorage.setItem("scroll", scroll);
  });
</script>

<div class="img" transition:fade={{ duration: 150, easing: sineOut }}>
  <img src={imgPath} alt="Programme Booklet" />
</div>

<svelte:window bind:scrollY={scroll} />

<style>
  img,
  .img {
    width: 100%;
  }
</style>
