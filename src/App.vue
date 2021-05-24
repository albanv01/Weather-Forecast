<template>
  <div id="app">
    <div class="container">
      <h1 class="title container">Current Weather + Forecast</h1>
      <WeatherForecast v-bind:llista-ciutats="Europa"></WeatherForecast>
      <WeatherForecast v-bind:llista-ciutats="Asia"></WeatherForecast>
      <WeatherForecast v-bind:llista-ciutats="Africa"></WeatherForecast>
      <WeatherForecast v-bind:llista-ciutats="America"></WeatherForecast>
      <WeatherForecast v-bind:llista-ciutats="Oceania"></WeatherForecast>

    </div>
  </div>
</template>

<script>
import WeatherForecast from "@/components/WeatherForecast";

export default {
  name: 'App',
  data: function () {
    return {
      selectedContinente: "Todos",
      toggled: false,
      fechaDia: null,
      fechaMes: null,
      fechaYear: null,
      continentes:[
        "Todos",
        "Europa",
        "Asia",
        "America",
        "Africa",
        "Oceania",
      ],
      Europa: [
        "Barcelona",
        "Lleida",
        "Zaragoza",
        "Sevilla",
        "Madrid",
        "París",
        "Viborg",
        "Londres",
        "Berlin",
      ],
      Asia:[
        "Lahore",
        "Beijing",
        "Kabul",
        "Tehran",
        "Seoul",
        "Tokyo",
        "Shanghai",
      ],
      America:[
        "New York",
        "New Jersey",
        "Toronto",
        "Medellin",
        "Buenos Aire",
      ],
      Africa:[
        "Nairobi",
        "Cairo",
        "Luanda",
        "Acra",
        "Dakar",
      ],
      Oceania:[
          "Sydney",
          "Brisbane",
          "Melbourne",
          "Canberra",
          "Auckland",
      ],
      monthNames: [
        "Enero",
        "Febrero",
        "Marzo",
        "Abril",
        "Mayo",
        "Junio",
        "Julio",
        "Agosto",
        "Septiembre",
        "Octubre",
        "Noviembre",
        "Diciembre"],
    }
  },
  components: {
    WeatherForecast
  }
}
</script>

<style>

</style>
