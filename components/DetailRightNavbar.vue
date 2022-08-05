<template>
  <div class="detail-right-navbar">
    <img src="~/assets/img/merlion.png"/>
    <div class="place-label" v-text="selectedLocation.label"></div>
    <div class="description">
      <div v-html="selectedLocation.description"></div>
      <img src="~/assets/img/icon/marina_location.png"/>
      <img src="~/assets/img/icon/marina_website.png"/>
    </div>
  </div>
</template>

<script>
export default {
  props: ['selectedLocation']
}
</script>

<style>

</style>
