<!--
cd tictactoe
npm run dev
-->

<script lang="ts">
  import logo from './assets/tictacno.png'
  import Grid from './lib/Grid.svelte'
</script>

<head>
  <title>tic tac no</title>
</head>

<main>
  <img src={logo} alt="tic tac no" />

  <div class="grid">
    <Grid />
  </div>  
  
  <p>
    this game is brought to you by Map UVic, whether they like it or not
  </p>

</main>

<style>

  .grid {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  :root {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
      Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }

  main {
    text-align: center;
    padding: 1em;
    margin: 0 auto;
  }

  img {
    height: 40%;
    width: 40%;
    padding-bottom: 50px;
  }

  p {
    max-width: 14rem;
    margin: 1rem auto;
    line-height: 1.35;
  }

  @media (min-width: 480px) {
    p {
      max-width: none;
    }
  }
</style>