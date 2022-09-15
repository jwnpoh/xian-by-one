<script>
  export let toggleText;
</script>

<button class:text-on={toggleText} class:text-off={!toggleText} on:click
  ><slot /></button
>

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
  }

  .text-on {
    background: rgba(148, 148, 148, 0.8);
    color: white;
  }
  .text-off {
    background: rgba(40, 40, 40, 0.8);
    color: rgb(153, 153, 153);
  }
</style>
