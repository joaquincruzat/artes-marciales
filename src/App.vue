<template>
  <div id="app">
 <nav class="navbar navbar-expand navbar-dark bg-dark">
  <router-link :to="{name:'home'}" class="navbar-brand">Home</router-link>
  <div  id="navbarNav">
    <ul class="navbar-nav">
      <li class="nav-item active">
        <router-link :to="{name:'search'}" class="nav-link">Buscador</router-link>
      </li>
      <li class="nav-item active">
        <router-link :to="{name:'list'}" class="nav-link">Lista de peleadores</router-link>
      </li>
    </ul>
  </div>
</nav>
<section>
    <router-view/>
  </section>
  </div>
</template>
<script>

export default {
  name: "App",
};
</script>
<style>

</style>
