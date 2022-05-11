<script lang="ts">
  export let restartGame;
</script>

<button on:click={restartGame}>restart game</button>

<style>

  button {
    width: 100px;
    height: 100px;
    margin: 10px;
    font-family: inherit;
    font-size: 22px;
    color: #ff3e00;
    background-color: rgba(255, 62, 0, 0.1);
    border-radius: 2em;
    border: 2px solid rgba(255, 62, 0, 0);
    outline: none;
    font-variant-numeric: tabular-nums;
    cursor: pointer;
  }

  button:focus {
    border: 2px solid #ff3e00;
  }

  button:active {
    background-color: rgba(255, 62, 0, 0.2);
  }

</style>