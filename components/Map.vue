<template>
  <GMap
    ref="gMap"
    language="en"
    :cluster="{options: {styles: clusterStyle}}"
    :center="{lat: pinLocation[0].langitude, lng: pinLocation[0].longitude}"
    :options="{fullscreenControl: false}"
    :zoom="zoomSetting"
  >
    <GMapMarker
      v-for="location in pinLocation"
      :key="location.keyword"
      :position="{lat: location.langitude, lng: location.longitude}"
      :options="{icon: location.keyword === selectedLocation.keyword ? '' : ''}"
      @click="$emit('location', location.keyword)"
    >
      <GMapInfoWindow :options="{maxWidth: 200}">
        <code>
          lat: {{ location.langitude }},
          lng: {{ location.longitude }}
        </code>
      </GMapInfoWindow>
    </GMapMarker>
  </GMap>
</template>

<script>
export default {
  props: ['selectedLocation', 'pinLocation'],
  data() {
    return {
      circleOptions: {},
      clusterStyle: [
        {
          url: "https://developers.google.com/maps/documentation/javascript/examples/markerclusterer/m1.png",
          width: 56,
          height: 56,
          textColor: "#fff"
        }
      ]
    }
  },
  computed: {
    zoomSetting(){
      if(this.selectedLocation && Object.keys(this.selectedLocation).length){
        return 17;
      }
      return 15;
    }
  }
}
</script>

<style>

</style>
