<script lang="ts">
  export let xIsNext;
  export let end;
  let status;

  $: if (end) {
    if (end == "draw") {
      status = "it's a draw";
    } else {
      status = "winner: " + end;
    }
  } else {
    status = "current player: " + (xIsNext ? "X" : "O")
  }
</script>

<h3>{status}</h3>