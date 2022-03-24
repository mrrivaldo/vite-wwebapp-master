<script setup>
import Search from "./Search.vue";
</script>

<template>
  <div class="home-container d-flex">
    <div
      class="display-3"
      style="margin-left: -10vw; font-weight: bold; margin-top: 1rem "
    >
      Weather App
    </div>
    <p
      class="text-muted"
      style="
        margin-left: -22em;
        font-weight: 600;
        font-size: 20px;
        margin-top: 20vh;
      "
    >
      We are the weather forecast system<br />We provide the weather information
      using API<br />The API will give you the most accurate result
    </p>

    <Search />
  </div>
</template>
