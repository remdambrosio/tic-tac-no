<script lang="ts">
  export let hit;
  let message;

  $: if (hit == "start") {
      message = "~ both players have 75% accuracy ~";
    } else if (hit == "yes") {
      message = "~ BAMALAM, that was a HIT! ~";
    } else {
      message = "~ OH NO, that was a MISS! ~";
    }
</script>

<h3>{message}</h3>