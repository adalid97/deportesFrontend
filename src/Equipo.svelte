<script>
  import Boton from "./Boton.svelte";
  
  export let equipo = {};
</script>

<style>
  .title {
    font-weight: bold;
  }
  .card {
    background-color: #111010;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    border-radius: 5px;
    transition: 0.3s;
    padding: 10px;
    margin: 10px;
  }

  .card:hover {
    box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.4);
  }

  input {
    background-color: inherit;
    padding: 10px;
    font-size: 14px;
    color: white;
    border: 0;
    outline: none;
    margin-left: 5px;
    margin-bottom: 4px;
    max-width: 140px;
  }

  input[type="number"] {
    text-align: right;
    width: 100px;
  }
  input:focus {
    background-color: cornflowerblue;
  }

  input:required:invalid,
  input:focus:invalid {
    background-color: lightpink;
  }
</style>

<div class="card" on:click>
  <input bind:value={equipo.nombre} placeholder="Nombre" class="title" />
  <input bind:value={equipo.pais} placeholder="Pais" class="title" />
  <input bind:value={equipo.socios} placeholder="Socios" type="number" min="0" max="100000"/>
  <input bind:value={equipo.titulos} placeholder="Titulos" type="number" min="0" max="100"/>
  <slot />
</div>
