<template>
  <nav class="navbar">
    <div class="main-navbar">
      <div class="main-navbar-item" :class="getActivePage == 'index' ? 'active': ''">
        <img src="~/assets/img/icon/browse.png" class="main-navbar-icon"/>
        <label>Browse</label>
      </div>
      <div class="main-navbar-item">
        <img src="~/assets/img/icon/sa.png" class="main-navbar-icon"/>
        <label>Suggest<br/>Attraction</label>
      </div>
      <div class="main-navbar-item">
        <img src="~/assets/img/icon/videos.png" class="main-navbar-icon"/>
        <label>Videos</label>
      </div>
      <div class="main-navbar-item">
        <img src="~/assets/img/icon/blog.png" class="main-navbar-icon"/>
        <label>Blog</label>
      </div>
      <div class="main-navbar-item">
        <img src="~/assets/img/icon/i.png" class="main-navbar-icon"/>
        <label>About</label>
      </div>
    </div>
    <div v-if="getActivePage == 'index'" class="browse-detail-navbar">
      <div class="filter">
        <select>
          <option>Filter by favorite</option>
        </select>
      </div>
      <ul class="menu-detail-list">
        <li @click="$emit('location', 'merlion')" :class="selectedLocation.keyword == 'merlion' ? 'active': ''">Merlion</li>
        <li @click="$emit('location', 'marina')" :class="selectedLocation.keyword == 'marina' ? 'active': ''">Marina Bay Sands
          <ul>
            <li>ArtScience Museum</li>
            <li>Marina Bay Sands Skypark</li>
            <li>Double Helix Bridge</li>
          </ul>
        </li>
        <li @click="$emit('location', 'garden')" :class="selectedLocation.keyword == 'garden' ? 'active': ''">Garden By the Bay</li>
        <li @click="$emit('location', 'town')" :class="selectedLocation.keyword == 'town' ? 'active': ''">China Town</li>
        <li @click="$emit('location', 'museum')" :class="selectedLocation.keyword == 'museum' ? 'active': ''">Asian Civilisations Museum</li>
        <li @click="$emit('location', 'quay')" :class="selectedLocation.keyword == 'quay' ? 'active': ''">Clarke Quay</li>
        <li @click="$emit('location', 'fort')" :class="selectedLocation.keyword == 'fort' ? 'active': ''">Fort Canning Park</li>
        <li @click="$emit('location', 'flyer')" :class="selectedLocation.keyword == 'flyer' ? 'active': ''">Singapore Flyer</li>
        <li @click="$emit('location', 'orchad')" :class="selectedLocation.keyword == 'orchad' ? 'active': ''">Orchad Road</li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  props: ['selectedLocation'],
  computed: {
    getActivePage(){
      return this.$nuxt.$route.name;
    }
  }
}
</script>

<style>

</style>
