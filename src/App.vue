<template>
  <GoogleMap
      :api-key="apiKey"
      style="width: 100%; height: 100%"
      :center="center"
      :zoom="15"
  >
    <gmap-custom-marker :marker="center">
      <img height="75" alt="custom marker" src="https://cdn.rebrickable.com/media/thumbs/mocs/moc-91667.jpg/1000x800.jpg?1635782553.4022405"/>
    </gmap-custom-marker>
  </GoogleMap>
</template>

<script>
import {GoogleMap} from 'vue3-google-map'
import GmapCustomMarker from './gmap-custom-marker'

export default {
  name: 'App',
  components: {
    GoogleMap,
    GmapCustomMarker
  },
  data() {
    return {
      center: {
        lat: 50.6272265,
        lng: 3.0571581
      }
    }
  },
  computed: {
    apiKey() {
      return process.env.VUE_APP_GMAP_API_KEY
    }
  }
}
</script>

<style>
html, body, #app {
  width: 100%;
  height: 100%;
  margin: 0;
  padding: 0;
}
</style>
