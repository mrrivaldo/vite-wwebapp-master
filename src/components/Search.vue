<template>
  <!-- Search -->
  <div class="search-bar d-flex align-self-start">
    <input
      style="
        border-radius: 0px 16px 0px 16px;
        width: 15vw;
        margin-left: -25em;
        margin-top: 50vh;
      "
      class="form-control"
      type="text"
      placeholder="Search..."
      v-model="keyword"
    />
    <button
      style=""
      class="btn btn-dark text-white align-self-end ml-3"
      type="button"
      @click="getData()"
    >
      Find Your Location
    </button>
  </div>
  <!-- WEATHER INFO -->
  <div class="weather-info" style="margin-left: 10em">
    <div class="weather-box">
      <div class="info-temp" v-if="name">
      <p
        class="location font-weight-bold mt-5 ml-2 mb-1"
        style="
          font-size: 45px;
          text-shadow: -1px 10px 8px rgba(0, 0, 0, 0.25);
          color: rgb(52, 58, 64);
        "
      >
        {{ name }}
      </p>

        <p
         
          class="temperature fw-bold text-white ml-n5 pb-3 p-2"
          style="
            background-color: rgb(52, 58, 64);
            font-size: 86px;
            text-shadow: 4px 5px rgba(0, 0, 0, 0.35);
            border-radius: 20px;
            box-shadow: 4px 5px rgba(0, 0, 0, 0.35);
          "
        >
          {{ temp }} C
        </p>
        <p
          class="description fw-bold mb-4 pb-4 ml-n4"
          style="
            text-align: center;
            color: rgb(52, 58, 64);
            font-size: 25px;
            font-style: italic;
            text-shadow: 0px 5px 9px rgba(0, 0, 0, 0.35);
          "
        >
          {{ desc }}
        </p>
      </div>
     <div class="notfound" style="margin-top: 10em;" v-else>
      <h1 class="mt-2">NOT FOUND</h1>
      <span class="text-muted m-4">Please input valid location</span>
     </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
const name = ref("");
const temp = ref("");
const desc = ref("");
const wind = ref("");
const keyword = ref("");


// GET API FUNCTION
async function getData() {
  console.log("GET API");
  
  const response = await fetch(
    `https://api.openweathermap.org/data/2.5/weather?q=${keyword.value}&appid=ff447018ac79a3e20a418d9810e43135&units=metric`,
    {
      method: "GET",
    }
  );
  const data = await response.json();
  console.log(data);
  name.value = data.name;
  temp.value = data.main.temp;
  desc.value = data.weather[0].description;
  wind.value = data.wind.speed;
 
}

getData();
</script>

<script>
export default {
  name: "Search",
};
</script>
