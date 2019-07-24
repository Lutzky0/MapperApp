<template>
  <div class="MapComp">
    
    <div ref="map" id="map"></div>
  
  </div>
</template>



<script>
import { Component, Vue } from 'vue-property-decorator';
import { Geolocation } from '@ionic-native/geolocation';
import { google } from 'google-maps';
// import MapSearch from "./MapSearch.vue";
// import TravelMap from "./TravelMap.vue";
//import GoogleMapMarker from "./GoogleMapMarker.vue";
@Component({
  components: {
    // TravelMap,
    //GoogleMapMarker,
    //MapSearch
  },
})


export default class MapComp extends Vue {

 // Some code from: https://developers.google.com/maps/documentation/javascript/tutorial

  mounted() {


   this.map = new window.google.maps.Map(this.$refs.map, {
          center: {lng: 50, lat: 50},
          zoom: 20
        });


     function updatePos(pos){
        console.log(pos.coords.latitude);
        this.map = new window.google.maps.Map(document.getElementById("map"), {
          center: {lat: pos.coords.latitude, lng: pos.coords.longitude},
          zoom: 20
        });

    }


 if (navigator.geolocation) {
          navigator.geolocation.getCurrentPosition(updatePos)};

  }
  
};
</script>


<style>

#map{
    height: 800px;
}

</style>
