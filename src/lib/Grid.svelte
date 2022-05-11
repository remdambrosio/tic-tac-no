<script lang="ts">
  import Dot from "./Dot.svelte";
  import Display from "./Display.svelte";
  import Restart from "./Restart.svelte";
  import Accuracy from "./Accuracy.svelte";

  let dots = [null, null, null, null, null, null, null, null, null];
  let xIsNext = true;
  let end = null;
  let hit = "start";

  function handleClick(i) {
    if (!dots[i]) {
      if (Math.floor(Math.random() * 4) != 0) {
        dots[i] = xIsNext ? "X" : "O";
        xIsNext = !xIsNext;
        end = calculateEnd(dots);
        hit = "yes"
      } else {
        xIsNext = !xIsNext;
        hit = "no"
      }
    }
  }

  function calculateEnd(dots) {
    const winningCombo = [
      [0, 1, 2],
      [3, 4, 5],
      [6, 7, 8],
      [0, 3, 6],
      [1, 4, 7],
      [2, 5, 8],
      [0, 4, 8],
      [2, 4, 6]
    ];
    for (let i = 0; i < winningCombo.length; i++) {
      const [a, b, c] = winningCombo[i];
      if (dots[a] && dots[a] === dots[b] && dots[a] === dots[c])
        return `${dots[a]}`;
    }

    const isDraw = dots.every(square => square !== null);
    return isDraw ? "draw" : null;
  }

  function restartGame() {
    dots = [null, null, null, null, null, null, null, null, null];
    xIsNext = true;
    end = null;
    hit = "start";
  }

</script>

<div class="grid">

  <p><Accuracy hit = {hit}/></p>

  <br>

  {#each dots as dot, i}
    <Dot value = {dot} handleClick = {() => handleClick(i)} />
  {/each}

  <br>

  <p><Display xIsNext = {xIsNext} end = {end}/></p>

  <p>
    {#if end}
      <Restart restartGame = {restartGame}/>
    {/if}
  </p>

</div>

<style>
  .grid {
    display: flex;
    flex-wrap: wrap;
    width: 360px;
    align-items: center;
    justify-content: center;
  }
</style>