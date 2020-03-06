<script>
  import { onMount, getContext } from "svelte";
  import { jsonData } from "./store.js";

  import Buscar from "./Buscar.svelte";
  import Equipo from "./Equipo.svelte";
  import Boton from "./Boton.svelte";

  const URL = getContext("URL");

  let busqueda = "";
  let equipo = {};

  onMount(async () => {
    const response = await fetch(URL.equipos);
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
    img {

    }
  }
</style>

<h1>
  <img alt="Icono platos" width="50px" src="/platos.png" />
  <span>Equipos</span>
</h1>
<Buscar bind:busqueda />

<br />

<h2>Añadir un nuevo equipo</h2>
<div>
  <Equipo bind:equipo>
    <br />
    <br />
    <Boton documento={equipo} tipo="insertar" coleccion="equipos" />
  </Equipo>
</div>

<br />

<h2>Lista de equipos</h2>
<div class="container">
  {#each datos as equipo}
    <Equipo {equipo}>
      <div style="text-align: left">
        <Boton documento={equipo} tipo="modificar" coleccion="equipos" />
        <Boton documento={equipo} tipo="eliminar" coleccion="equipos" />
      </div>
    </Equipo>
  {/each}
</div>
