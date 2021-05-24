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
      ],
      Asia:[
        "Lahore",
        "Beijing",
        "Kabul",
        "Tehran"
      ],
      America:[
        "Mountain View",
        "New Jersey",
        "Panama",
      ],
      Africa:[
        "Lagos",
        "Cairo",
        "Luanda",
      ],
      Oceania:[
          "Sydney",
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
