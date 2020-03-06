<script>
  import { setContext } from "svelte";
  import { Router } from "svelte-routing";
  import Menu from "./Menu.svelte";
  import Contenido from "./Contenido.svelte";
  import Pie from "./Pie.svelte";

  const URL = {
    equipos: "https://deportes-daw.herokuapp.com/api/jugadoresequipos/",
    jugadores: "https://deportes-daw.herokuapp.com/api/jugadores/"
  };

  setContext("URL", URL);
</script>

<Router>
  <Menu />
  <Contenido />
</Router>
<Pie />
