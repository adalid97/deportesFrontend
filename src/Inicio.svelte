<script>
  import { Link } from "svelte-routing";
</script>

<style>
  h1,
  div,
  p {
    padding: 3px;
  }
  div {
    padding: 30px;
  }

  .bloque {
    display: flex;
    flex-direction: column;
  }
  .resumen {
    display: flex;
    flex-wrap: wrap;    
    padding: 5px;
    margin: 0 0 15px;
    border: 1px solid #000;
    border-radius: 4px;
    box-shadow: 0 0 3px rgba(0, 0, 0, 0.19);
    border: 1px solid rgb(245, 177, 31);
    border-radius: 4px;
  }

  .opcion {
    display: flex;   
    word-break: break-word;
    padding: 0 10px;
    font-size: 14px;
    font-weight: 700;
    text-shadow: 0 1px 0 rgba(0, 0, 0, 0.1);
    font-family: sans-serif;
    color: white;
    border-radius: 4px;
    background: black;
    min-width: 140px;
    padding: 10px;
  }

  .descripcion {
    font-size: 14px;
    flex: 1 1 auto;
    word-break: break-word;
    font-family: sans-serif;
    color: #3b4151;
    padding-top: 10px;
    padding-left: 10px;
  }
</style>

<h1>Deportes Frontend</h1>
<p>
  <small>
    <b>Progressive Web App (PWA)</b>
  </small>
</p>
<p>

</p>
<p>Esta SPA (Single Page Application) ofrece 3 opciones:</p>

<div class="bloque">
  <Link to="/">
    <div class="resumen">
      <span class="opcion">🏟 Inicio</span>
      <span class="descripcion">Página de Inicio.</span>
    </div>
  </Link>

  <Link to="/equipos">
    <div class="resumen">
      <span class="opcion">🏆 Equipos</span>
      <span class="descripcion">
        Operaciones CRUD de equipos en una BD.
      </span>
    </div>
  </Link>

  <Link to="/jugadores">
    <div class="resumen">
      <span class="opcion">🏃 Jugadores</span>
      <span class="descripcion">
        Operaciones CRUD de jugadores en una BD.
      </span>
    </div>
  </Link>

</div>
<p>
  <small>
    <b>
      Código fuente en
      <a href="https://github.com/adalid97/deportesFrontend">
        https://github.com/adalid97/deportesFrontend
      </a>
    </b>
  </small>
</p>
