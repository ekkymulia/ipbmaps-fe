<script>
import { Loader } from '@googlemaps/js-api-loader'

export default {
  data() {
    return {
      loader: null,
      mapOptions: {
        center: {
          lat: 0,
          lng: 0
        },
        zoom: 4
      }
    }
  },
  mounted() {
    this.loader = new Loader({
      apiKey: '',
      version: 'weekly',
      libraries: ['places']
    })

    this.loader.load().then(() => {
      const map = new google.maps.Map(document.getElementById('map'), this.mapOptions)
    })
  }
}
</script>
<template>
  <div class="map-wrapper">
    <div id="map"></div>
  </div>
</template>
<style scoped>
#map {
  position: fixed !important;
  height: 75% !important;
  width: 100% !important;
  z-index: -10 !important;
  margin: 0;
  padding: 0;
}
</style>
