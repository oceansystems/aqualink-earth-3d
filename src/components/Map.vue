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
        let options = {atmosphere: true, sky: true, center: [0, 0], zoom: 0};
        let map = new WE.map('map', options);

        let satellite = WE.tileLayer(
        'https://api.mapbox.com/styles/v1/drewjgray/ck0bpygie40jp1crykgq18klw/tiles/{z}/{x}/{y}@2x?access_token=pk.eyJ1IjoiZHJld2pncmF5IiwiYSI6ImNqdTRxMzgwYzBraGg0ZXM3ZmIzOWExbHIifQ.wvV7ivQng_NR5L16xhl-DA', {
            tileSize: 512,
            zoomOffset: -1,
        }).addTo(map);

        let sst = WE.tileLayer(
            'https://gis.unep-wcmc.org/arcgis/rest/services/marine/WCMC_035_MeanSeaSurfaceTemperature2015/MapServer/tile/{z}/{y}/{x}'
        ).addTo(map);

        let basemaps ={
            'Satellite': satellite,
        }

        let overlays = {
            'SST': sst,
        }

        // L.control.layers(basemaps, overlays).addTo(map);

        let marker = WE.marker([37.898117, -122.676366]).addTo(map);
        marker.bindPopup("<b>Bolinas</b><br>")
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#map {
  width: 100%;
  height: 100vh;
  background: black;
}

</style>
