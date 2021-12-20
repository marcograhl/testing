<script>
  import Snowman from "./Snowman.svelte";

  let seed = new Date().getTime();
</script>

<svelte:window on:click={() => seed = Math.floor((new Date().getTime() + Math.random() * 1000000000000) / 10000000)} />

<main>
	<Snowman {seed} />
</main>


<style>
  main {
    font-family: sans-serif;
    text-align: center;
    background: #ceeaf3;
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
  }
</style>
