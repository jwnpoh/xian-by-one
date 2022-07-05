<script>
  export let boxColor;
</script>

<div class="card" style="background-color: {boxColor};" on:click />

<style>
  .card {
    display: flex;
    flex: 1 1 auto;
    justify-content: space-evenly;
    align-items: center;
    width: 40%;
    height: 40%;
    box-sizing: border-box;
    padding: 10px;
    margin: 15px;
    border-radius: 10px;
    box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
  }
</style>
