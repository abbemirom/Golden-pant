<template>
  <div class="row mt-5">
    <div style="height: 500px; width: 500px" ref="map"></div>
  </div>
</template>


<script>
export default {
  head () {
    return {
      title: 'Properties',
      script: [{
        src: "https://maps.googleapis.com/maps/api/js?key=XXX",
        hid: "map",
        defer: true,
      }]
    }
  },

  mounted () {
    const mapOptions = {
      zoom: 18,
      center: new window.google.maps.LatLng(43.758773, -79.391785),
      disableDefaultUI: true,
      zoomControl: true
    }

    const map = new window.google.maps.Map(this.$refs.map, mapOptions)
    const position = new window.google.maps.LatLng(43.758773, -79.391785)
    const marker = new window.google.maps.Marker({ position })
    marker.setMap(map)
  },
}
</script>

<style>
</style>
