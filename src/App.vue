<template>
  <div id="app">
    <img id="logo" alt="MapApp logo" src="./assets/logo2.png">
    <Mapper/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Mapper from './components/Mapper.vue';

@Component({
  components: {
    Mapper,
  },
})
export default class App extends Vue {}

</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#logo{
  height:100px;
}
</style>
