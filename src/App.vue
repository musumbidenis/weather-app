<template>
  <div id="app">
    <main>
      <div class="search-box">
        <input type="text" placeholder="Search.." class="search-bar">
      </div>

      <div class="weather-wrap">
        <div class="location-box">
          <div class="location">Mombasa, Kenya</div>
          <div class="date">Monday, 08 2020</div>
        </div>

        <div class="weather-box">
          <div class="temp">9C</div>
          <div class="weather">Rain</div>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
export default {
  name: 'App',
  data(){
    return{
      api_key: "cb7db5fe34f9eb92a11870c8082cc5d5",
      url_base: "api.openweathermap.org/data/2.5/",
    }
  }
}
</script>

<style>

</style>
