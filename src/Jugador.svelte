<script>
  export let jugador = {};
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

<div class="card">
  <input bind:value={jugador.nombre} placeholder="Nombre" class="title" />
  <input bind:value={jugador.apellidos} placeholder="Apellidos" class="title"/>
  <input bind:value={jugador.edad} placeholder="Edad" type="number" max="99" min="0"/>
  <input bind:value={jugador.equipo} placeholder="Equipo" class="title"/>
  <slot />
</div>
