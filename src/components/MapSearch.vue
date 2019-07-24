<template>
  <div class="MapSearch">
    
    <input ref="autocomplete" 
        placeholder="Search" 
        class="search-location"
        onfocus="value = ''" 
        type="text" 
        id="autoComp"/>
       
  
  </div>
</template>



<script>
import { Component, Vue } from 'vue-property-decorator';
import { Geolocation } from '@ionic-native/geolocation';
import { google } from 'google-maps';
// import TravelMap from "./TravelMap.vue";
import GoogleMapMarker from "./GoogleMapMarker.vue";
@Component({
  components: {
    // TravelMap,
    GoogleMapMarker
  },
})


export default class MapSearch extends Vue {

 //Some code from: https://medium.com/dailyjs/google-places-autocomplete-in-vue-js-350aa934b18d

  mounted() {

    this.autocomplete = new window.google.maps.places.Autocomplete(
      (this.$refs.autocomplete),
      {types: ['geocode']}
    );

    


this.autocomplete.addListener('place_changed', () => {
  let place = this.autocomplete.getPlace();
  let ac = place.address_components;
  let _lat = place.geometry.location.lat();
  let _lon = place.geometry.location.lng();
  let city = ac[0]["short_name"];
  
  console.log(`The user picked ${city} with the coordinates ${_lat}, ${_lon}`);
 
  this.map = new window.google.maps.Map(document.getElementById("map"), {
          center: {lat: _lat, lng: _lon},
          zoom: 20
        });

let marker = new window.google.maps.Marker({position: {lat: _lat, lng: _lon}, map: this.map});


});

 
  
}

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.search-location {
  display: block;
  width: 60vw;
  margin: 0 auto;
  margin-top: 5vw;
  font-size: 20px;
  font-weight: 400;
  outline: none;
  height: 30px;
  line-height: 30px;
  text-align: center;
  border-radius: 10px;
    margin-bottom: 100px;
}
</style>
