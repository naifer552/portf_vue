
<template>
  <Suspense>
    <!--Se debe suspender una presentación mientras inicia la otra-->
    <template #default><!--Este es el template principal-->
      <Home />
    </template>
    <template #fallback><!--Este es el template de iniciación-->
      <SplashScreen />
    </template>
  </Suspense>


</template>

<script>
import SplashScreen from "@/components/SplashScreen.vue"; /* Se importa o busca el elemento SplashScreen */
/* Como sera una aplicación donde es posible que las pagina principal cargue muy rapido se debe importar un 
elemento asyncrono que permita detener la pagina principal un momento para mostrar el splashScreen, por eso
se carga defineAsyncComponent, que es un componenete de vue */
import { defineAsyncComponent } from "vue";
export default {
  components: { /* Se incresan los componentes a utilizar */
    SplashScreen,
    Home: defineAsyncComponent( /* Se le indica que carge el home despues de pasados unos milisegundos, en este caso 5000 */
      () =>
      new Promise ((resolve) => { /* se define una promesa, para que se ejecute y espere los 5000 milisegundos */
                setTimeout(() => {
                  resolve(import("./components/Home.vue"));
        }, 5000);
      })

    ),
  },
};
</script>
/** */
<style>
html,
body,
.app {
  min-height: 100vh;
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
}
* {
  --brand-green: #04b500;
  --brand-blue: #0689b0;
}

</style>
