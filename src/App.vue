<template>
  <div id="app">
    <main>
      <div class="search-box">
        <input 
          type="text"
          class="search-bar" 
          placeholder="Search.."
          v-model="query"
          @keypress="fetchWeather"
        />
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
      query:'',
      weather:{}
    }
  },
  methods: {
    fetchWeather (e) {
      if (e.key == "Enter") {
        fetch(`${this.url_base}weather?q=${this.query}&units=metric&APPID=${this.api_key}`)
          .then(res => {
            return res.json();
          }).then(this.setResults);
      }
    },
    setResults (results) {
      this.weather = results;
    },
    // dateBuilder () {
    //   let d = new Date();
    //   let months = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"];
    //   let days = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"];
    //   let day = days[d.getDay()];
    //   let date = d.getDate();
    //   let month = months[d.getMonth()];
    //   let year = d.getFullYear();
    //   return `${day} ${date} ${month} ${year}`;
    // }
  }
}

</script>

<style>

</style>
