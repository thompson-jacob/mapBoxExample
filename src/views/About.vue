<template>
  <div id="map" style="width: 400px; height: 300px;"></div>
</template>

<script>
/* global mapboxgl */
export default {
  data: function()  {
      places: [
        { lat: -25.363, lng: 131.044, description: "A place in Australia" },
        { lat: -33.8675, lng: 151.207, description: "The main city!" },
      ],
  },

  mounted: function() {
    places.forEach(function(i) {
      console.log(i)
    });
    this.setupMap();
  },
  methods: {
    setupMap: function() {
      mapboxgl.accessToken = process.env.VUE_APP_MAPBOX_API_KEY;
      var map = new mapboxgl.Map({
        container: "map",
        style: "mapbox://styles/mapbox/streets-v11",
        center: [-87.6298, 41.8781],
        zoom: 4,
      });
      console.log(map);
      var popup = new mapboxgl.Popup({ offset: 25 }).setText("You are Here");
      var marker = new mapboxgl.Marker()
        .setLngLat([-87.6298, 41.8781])
        .setPopup(popup)
        .addTo(map);
      console.log(marker);
      console.log(popup);
    },
  },
};
</script>
