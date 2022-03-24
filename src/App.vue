<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup

import navbar from "./components/navbar.vue";
</script>

<template>
  <div class="main-container d-flex justify-content-center">
    <div
      class="container-app d-flex align-items-center"
      style="
        background-color: whitesmoke;
        width: 1000px;
        height: 720px;
        margin-top: 100px;
        border-radius: 71px;
      "
    >
      <navbar />
      <router-view />
    </div>
  </div>
</template>

<style>
#app {
  background-color: rgb(206, 227, 233);
  width: 1920px;
  height: 1080px;
}
</style>
