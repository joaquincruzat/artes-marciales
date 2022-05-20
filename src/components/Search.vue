<template >
  <div>
    <h4 class="title-search">Buscar un peleador por id</h4>
    <form class="form-inline form-search" @submit.prevent="findPeleadores(id)">
      <div class="form-group mx-sm-3 mb-2">
        <input
          type="text"
          v-model="id"
          class="form-control"
          placeholder="Ingrese ID"
        />
      </div>
      <button type="submit" class="btn btn-primary mb-2">buscar</button>
    </form>
    <div></div>
  </div>
</template>

<script>

export default {
  name: "Search",

  data() {
    return {
      id: "",
    };
  },
  methods: {
  findPeleadores (id){this.$router.push(`/list/${id}`)
},
}
}
</script>

<style>

.title-search {
  text-align: center;
  margin-bottom: 25px;
}
.form-search {
    text-align: center;
    justify-content: center;
}

</style>