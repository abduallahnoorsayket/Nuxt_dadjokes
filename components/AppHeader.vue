<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
      <a class="navbar-brand">Dad Jokes</a>

      <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
        <div class="navbar-nav">
          <nuxt-link to="/" class="nav-item nav-link active"> Home</nuxt-link>
          <nuxt-link to="/Jokes" class="nav-item nav-link active">
            Jokes</nuxt-link
          >
          <nuxt-link to="/about" class="nav-item nav-link active">
            About</nuxt-link
          >
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: "AppHeader",
};
</script>

<style scoped>
.navbar-nav a {
  display: inline-block;
  /* background: #333; */
  color: #fff;
  padding: 0.3rem 1rem;
  margin-right: 0.5rem;
}
</style>
