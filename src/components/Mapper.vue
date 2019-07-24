<template>
  <div class="Mapper">
    <MapSearch/>
    <MapComp/>
  </div>
</template>



<script>
import { Component, Vue } from 'vue-property-decorator';
import { Geolocation } from '@ionic-native/geolocation';
import { google } from 'google-maps';
import MapSearch from "./MapSearch.vue";
import MapComp from "./MapComp.vue";

@Component({
  components: {
    MapSearch,
    MapComp
  },
})


export default class Mapper extends Vue {

 
  
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
*, *::after, *::before {
  margin: 0;
  padding: 0;
  box-sizing: inherit;
}

body {
  background-color: #dcdde1;
  color: #2f3640;
  padding: 3rem;
}
</style>
