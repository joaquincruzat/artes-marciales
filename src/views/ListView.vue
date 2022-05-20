<template>
  <div class="list">
    <h1 class="title-list">Listado de peleadores</h1>
    <ul>
      <li
        v-for="peleador in peleadores"
        :key="peleador.id"
        @click="findPeleadores(peleador.id)"
      >
        {{ peleador.nombre }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data: () => ({
    peleadores: [],
  }),
  created() {
    fetch("/peleadores.json")
      .then((res) => res.json())
      .then((peleadores) => {
        this.peleadores = peleadores;
      });
  },
  methods: {
    findPeleadores(id) {
      this.$router.push(`/list/${id}`);
    },
  },
};
</script>

<style>
li {
  cursor: pointer;
}
.title-list {
  margin-left: 15px;
  margin-top: 15px;
}

</style>