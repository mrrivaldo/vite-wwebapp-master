<template>
  <!-- NAVIGATION BAR -->
  <nav class="navbar">
    <div
      class="navbar-detail d-flex"
      style="margin-top: -40vw; margin-left: 3vw"
    >
      <router-link to="/" class="nav-link text-dark">Home</router-link>
      <router-link to="/about" class="nav-link text-dark">About</router-link>
    </div>
  </nav>
</template>

<script>
export default {
  name: "navbar",
};
</script>

<style>
.nav-link {
  padding-right: 2vw;
  font-weight: bold;
  font-size: 20px;
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
}
</style>
