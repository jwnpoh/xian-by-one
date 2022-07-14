<script>
  import { onMount, beforeUpdate, afterUpdate, onDestroy } from "svelte";

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

<div class="img">
  <img src={imgPath} alt="Programme Booklet" />
</div>

<svelte:window bind:scrollY={scroll} />

<style>
  img,
  .img {
    width: 100%;
  }
</style>
