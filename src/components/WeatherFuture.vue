<template>



  <div class="card card-3">
    <div id="demo" class="carousel slide" data-ride="carousel">
      <div class="carousel-inner">
        <div class="carousel-item active">
          <div class="row">

            <div class="col">
              <div class="row row2"><img class="img-fluid" v-bind:src="'http://openweathermap.org/img/wn/'+icon_0+ '@2x.png' " /></div>
              <div class="row row3">Día 1</div>
              <div class="row row1">{{ciutatActual['list'][0]['main']['temp']}}&deg;</div>
            </div>
            <div class="col">
              <div class="row row2"><img class="img-fluid" v-bind:src="'http://openweathermap.org/img/wn/'+icon_1+ '@2x.png' " /></div>
              <div class="row row3">Día 2</div>
              <div class="row row1">{{ciutatActual['list'][8]['main']['temp']}}&deg;</div>
            </div>
            <div class="col">
              <div class="row row2"><img class="img-fluid"  v-bind:src="'http://openweathermap.org/img/wn/'+icon_2+ '@2x.png' " /></div>
              <div class="row row3">Día 3</div>
              <div class="row row1">{{ciutatActual['list'][12]['main']['temp']}}&deg;</div>
            </div>
            <div class="col">
              <div class="row row2"><img class="img-fluid"  v-bind:src="'http://openweathermap.org/img/wn/'+icon_3+ '@2x.png' " /></div>
              <div class="row row3">Día 4</div>
              <div class="row row1">{{ciutatActual['list'][20]['main']['temp']}}&deg;</div>
            </div>
            <div class="col">
              <div class="row row2"><img class="img-fluid"  v-bind:src="'http://openweathermap.org/img/wn/'+icon_4+ '@2x.png' " /></div>
              <div class="row row3">Día 5 </div>
              <div class="row row1">{{ciutatActual['list'][28]['main']['temp']}}&deg;</div>
              </div>
          </div>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
export default {
  name: "Forecast",
  props:{
    ciudadSelecionada:String,
  },

  data: function () {
    return {
      ciutatActual: "",
      icon_0: "",
      icon_1: "",
      icon_2: "",
      icon_3: "",
      icon_4: "",
    }
  },


  methods: {
    async getForecast(ciutat) {
      var url = "https://api.openweathermap.org/data/2.5/forecast?q=" + ciutat + "&units=metric&lang=es&appid=62e47abef67001c37a828b9b1edd1629";

      try {
        var response = await fetch(url);
        var data = await response.json();
        this.ciutatActual = data;
        this.icon_0 = data['list'][0].weather[0]['icon'];
        this.icon_1 = data['list'][8].weather[0]['icon'];
        this.icon_2 = data['list'][12].weather[0]['icon'];
        this.icon_3 = data['list'][20].weather[0]['icon'];
        this.icon_4 = data['list'][28].weather[0]['icon'];

      }
      catch(err) {
        console.log(err);
      }
    },
  },

  created: function() {
    console.log(this.fecha_1)
  },

  mounted: function () {
    this.getForecast(this.ciudadSelecionada);
  },

  watch: {
    ciudadSelecionada () {
      this.getForecast(this.ciudadSelecionada);
    }
  },



}

</script>

<style scoped>

</style>