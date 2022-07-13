<script>
  import { onMount, beforeUpdate, afterUpdate, onDestroy } from "svelte";

  export let imgPath;
  let scroll;

  onMount(() => {
    console.log("programme is mounted");
    scroll = localStorage.getItem("scroll");
    console.log("last y position is ", scroll);
    scrollTo({ top: scroll });
  });

  onDestroy(() => {
    console.log("programme is destroyed");
    console.log("y position is ", scroll);
    localStorage.setItem("scroll", scroll);
  });

  beforeUpdate(() => {
    console.log("before update");
  });

  afterUpdate(() => {
    console.log("after update");
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
