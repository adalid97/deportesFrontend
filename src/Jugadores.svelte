<script>
  import { onMount, getContext } from "svelte";
  import { jsonData } from "./store.js";

  import Buscar from "./Buscar.svelte";
  import Jugador from "./Jugador.svelte";
  import Boton from "./Boton.svelte";

  const URL = getContext("URL");

  let busqueda = "";
  let jugador = {};

  onMount(async () => {
    const response = await fetch(URL.jugadores); //CAMBIO
    const data = await response.json();
    $jsonData = data;
  });

  $: regex = new RegExp(busqueda, "i");
  $: datos = busqueda
    ? $jsonData.filter(item => regex.test(item.nombre))
    : $jsonData;
</script>

<style>
  .container {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: left;
    flex-wrap: wrap;
  }

  img {
    position: absolute;
  }

  span {
    margin-left: 60px;
  }

  @media screen and (max-width: 700px) {

    h2 {
      text-align: center;
    }
    .container {
      display: block;
    }
  }
</style>

<h1>
  <img alt="Icono platos" width="50px" src="/gorro.png" />
  <span>Jugadores</span>
</h1>
<Buscar bind:busqueda />

<br />

<h2>Añadir un nuevo jugador</h2>
<div>
  <Jugador bind:jugador>
    <br />
    <br />
    <Boton documento={jugador} tipo="insertar" coleccion="jugadors" />
  </Jugador>
</div>

<br />

<h2>Lista de Jugadores</h2>
<div class="container">
  {#each datos as jugador}
    <Jugador {jugador}>
      <div style="text-align: left">
        <Boton documento={jugador} tipo="modificar" coleccion="jugadors" />
        <Boton documento={jugador} tipo="eliminar" coleccion="jugadors" />
      </div>
    </Jugador>
  {/each}
</div>
