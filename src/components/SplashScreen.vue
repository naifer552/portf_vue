<!--El SplashScreen se utiliza para poner una presentación antes que se cargue la pagina principal-->
<template>
    <div class="splashscreen">
        <img 
        src="@/assets/naifer.jpeg" 
        alt="logo" />

        <h1><span>Naifer </span>Blanco</h1>

    </div>
</template>

<style scoped>
.splashscreen {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  height: 100vh;
}
h1 {
  color: var(--brand-blue);
}
h1 span {
  color: var(--brand-green);
}
</style>
