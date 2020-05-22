<template>
  <div id="map" class="container">
  </div>
</template>

// <script>

export default {
  name: 'Map',
  mounted() {
    this.initMap();
  },
  methods: {
    initMap() {
      let options = {atmosphere: true, center: [0, 0], zoom: 0};
      let earth = new WE.map('map', options);
      WE.tileLayer(
        'https://api.mapbox.com/styles/v1/drewjgray/ck0bpygie40jp1crykgq18klw/tiles/{z}/{x}/{y}@2x?access_token=pk.eyJ1IjoiZHJld2pncmF5IiwiYSI6ImNqdTRxMzgwYzBraGg0ZXM3ZmIzOWExbHIifQ.wvV7ivQng_NR5L16xhl-DA', {
            tileSize: 512,
            zoomOffset: -1,
        }).addTo(earth);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#map {
  width: 100%;
  height: 100%;
  background: black;
}

</style>
