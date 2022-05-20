<template>
  <div class="results">
    <div v-if="peleador">
      <h1>¡Peleador Encontrado!</h1>
      <p>ID: {{ peleador.id }}</p>
      <p>Nombre del peleador: {{ peleador.nombre }}</p>
      <img :src="peleador.imgSrc" alt="" />
    </div>
    <div v-if="!peleador">
      <h1>No se encontró al peleador que buscas. Intenta con otro ID.</h1>
      <br>
      <router-link to="/">Haga click aquí para volver al inicio</router-link>
    </div>
  </div>
</template>
<script>
export default {
  data: () => ({
    peleador: { nombre: "", imgSrc: "" },
  }),
  created() {
    const idPeleador = this.$route.params.id;
    fetch("/peleadores.json")
      .then((res) => res.json())
      .then((peleadores) => {
        this.peleador = peleadores.find(
          (item) => item.id === idPeleador || null
        );
      });
  },
};
</script>
<style>
.results {
  text-align: center;
  justify-content: center;
  margin-top: 50px;
}
</style>
