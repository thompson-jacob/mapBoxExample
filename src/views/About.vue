<template>
  <div id="map" style="width: 400px; height: 300px;"></div>
</template>

<script>
/* global mapboxgl */
export default {
  data() {
    return {};
  },

  mounted: function() {
    this.setupMap();
  },
  methods: {
    setupMap: function() {
      // mapboxgl.accessToken = process.env.VUE_APP_MAPBOX_API_KEY;
      mapboxgl.accessToken = "";
      var map = new mapboxgl.Map({
        container: "map",
        style: "mapbox://styles/mapbox/streets-v11",
        // center: [40.74, -74.54],
        zoom: 4,
      });
      console.log(map);
    },
  },
};
</script>
