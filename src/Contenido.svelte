<script>
  import { Route } from "svelte-routing";
  import Inicio from "./Inicio.svelte";
  import Equipos from "./Equipos.svelte";
  import Jugadores from "./Jugadores.svelte";
</script>

<style>
  main {
    padding: 30px;
  }

  @media screen and (max-width: 700px) {
    main {
      padding: 0px;
    }
  }
</style>

<main>
  <Route path="/" component={Inicio} />
  <Route path="/equipos" component={Equipos} />
  <Route path="/jugadores" component={Jugadores} />
</main>
