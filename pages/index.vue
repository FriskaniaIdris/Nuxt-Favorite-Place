<template>
  <div>
    <!-- Navbar Section -->
    <Navbar @location="setMapLocation" :selected-location="selectedLocation"></Navbar>
    <!-- End Navbar Section -->
    <!-- Content Section -->
    <section>
      <TopNavbar></TopNavbar>
      <Map :pin-location="pinLocation" :selected-location="selectedLocation" @location="showLocationDetail"></Map>
      <DetailRightNavbar v-show="showDetail" :selected-location="selectedLocation"></DetailRightNavbar>
    </section>
    <!-- End Content Section -->
  </div>
</template>

<script>
import TopNavbar from '../components/TopNavbar.vue';
import Map from '../components/Map.vue';
import DetailRightNavbar from '../components/DetailRightNavbar.vue';
export default {
  data(){
    return{
      showDetail: false,
      selectedLocation: {},
      pinLocation: [
        {
          keyword: 'merlion',
          label: 'Merlion',
          langitude: 1.286920,
          longitude: 103.854570,
          description: "The Merlion is the national personification of Singapore.<br/><br/>Its name combines 'mer' meaning the sea and 'lion'. The fish body represents Singapore's origin as a fishing village when it was called Temasek, which means 'sea town' in Javanese. The lion head represents Singapore's original name—Singapura—meaning 'lion city' or 'kota singa'.",
          location: "10 Bayfront Avenue, Singapore",
          website: "http://marinabaysands.com",
        },
        {
          keyword: 'marina',
          label: 'Marina By Sands',
          langitude: 1.283099,
          longitude: 103.860295,
          description: "Marina By Sands",
          location: "10 Bayfront Avenue, Singapore",
          website: "http://marinabaysands.com",
        },
        {
          keyword: 'garden',
          label: 'Garden By the Bay',
          langitude: 1.281790,
          longitude: 103.863954,
          description: "Garden By the Bay",
          location: "10 Bayfront Avenue, Singapore",
          website: "http://marinabaysands.com",
        },
        {
          keyword: 'town',
          label: 'China Town',
          langitude: 1.284193,
          longitude: 103.843362,
          description: "China Town",
          location: "10 Bayfront Avenue, Singapore",
          website: "http://marinabaysands.com",
        },
        {
          keyword: 'museum',
          label: 'Asian Civilisations Museum',
          langitude: 1.287466,
          longitude: 103.851424,
          description: "Asian Civilisations Museum",
          location: "10 Bayfront Avenue, Singapore",
          website: "http://marinabaysands.com",
        },
        {
          keyword: 'quay',
          label: 'Clarke Quay',
          langitude: 1.290555,
          longitude: 103.846188,
          description: "Clarke Quay",
          location: "10 Bayfront Avenue, Singapore",
          website: "http://marinabaysands.com",
        },
        {
          keyword: 'fort',
          label: 'Fort Canning Park',
          langitude: 1.295526,
          longitude: 103.845331,
          description: "Fort Canning Park",
          location: "10 Bayfront Avenue, Singapore",
          website: "http://marinabaysands.com",
        },
        {
          keyword: 'flyer',
          label: 'Singapore Flyer',
          langitude: 1.289332,
          longitude: 103.863152,
          description: "Singapore Flyer",
          location: "10 Bayfront Avenue, Singapore",
          website: "http://marinabaysands.com",
        },
        {
          keyword: 'orchad',
          label: 'Orchad Road',
          langitude: 1.302279,
          longitude: 103.837399,
          description: "Orchad Road",
          location: "10 Bayfront Avenue, Singapore",
          website: "http://marinabaysands.com",
        }
      ]
    }
  },
  components: { TopNavbar, Map, DetailRightNavbar },
  methods: {
    setMapLocation(keyword) {
      this.selectedLocation = this.pinLocation.find( location => {return location.keyword == keyword});
    },
    showLocationDetail(keyword) {
      this.selectedLocation = this.pinLocation.find( location => {return location.keyword == keyword});
      this.showDetail = true;
    }
  }
}
</script>
