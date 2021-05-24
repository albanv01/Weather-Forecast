<template>
  <div class="card card-1" style="right: auto">
    <div id="demo" class="carousel slide" data-ride="carousel">

          <div class="row">
            <div class="col-6">
              <div class="temp">{{ciutatActual['main']['temp']}}&deg;</div>
              <div class="location">{{ciutatActual.name}}</div>

              <small class="min">Temperatura mínima: {{ciutatActual['main']['temp_min']}}&deg;</small>
              <small class="max"> - Temperatura maxima: {{ciutatActual['main']['temp_max']}}&deg;</small>

            </div>
            <div class="col-6 justify-content-right">
              <img class="img-fluid" v-bind:src="'http://openweathermap.org/img/wn/' + icon + '@2x.png'"> </div>
          </div>

    </div>
  </div>
</template>

<script>
export default {
  name: "CurrentWeather",
  props: {
    ciudadSelecionada: String,
  },

  data: function () {
    return {
      ciutatActual: "",
      icon: "",
    }
  },

  methods: {
    async getWeather(ciutat) {
      var url = 'https://api.openweathermap.org/data/2.5/weather?q=' + ciutat + '&units=metric&lang=ca&appid=62e47abef67001c37a828b9b1edd1629';

      try {
        var response = await fetch(url);
        var data = await response.json();
        this.ciutatActual = data;
        this.icon = data['weather'][0]['icon'];
      } catch (err) {
        console.log(err);
      }
    }
  },


  mounted: function () {
    this.getWeather(this.ciudadSelecionada);
  },

  watch: {
    ciudadSelecionada() {
      this.getWeather(this.ciudadSelecionada);
    }
  },


}
</script>
