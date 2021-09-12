<script>
  import { onMount } from "svelte";
  const BACKEND_URI = import.meta.env.VITE_BACKEND_URI;
  let games = [];
  onMount(async () => {
    try {
      const res = await fetch(BACKEND_URI + "/games");
      games = await res.json();
    } catch (error) {
      console.log(error.response);
    }
  });
</script>

<h1>Hola</h1>
<div class="box-shawdow">
  {#each games as game}
    <div class="grid-games">
      <div class="box-game">
        {game.nombre}
      </div>
    </div>
  {/each}
</div>

<style>
  .box-shawdow {
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
    min-height: 97vh;
    height: 99.5%;
    background-color: #ffffff;
    width: 100%;
    max-width: 600px;
    margin: auto;
  }
  .grid-games {
    display: grid;
    grid-template-columns: 100%;
  }
  .box-game {
    margin-bottom: 10px;
    padding: 10px;
    background: rgb(3, 3, 66);
    color: white;
    font-weight: 900;
    text-align: center;
  }
</style>
