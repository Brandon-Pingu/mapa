<template>
  <Header></Header>
  <Mapa></Mapa>
  <Filtros></Filtros>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import Header from "./components/Header";
import Mapa from "./components/mapa";
import Filtros from "./components/Filtros";

export default {
  name: "App",
  components: {
    Header, Mapa, Filtros
  },
  data() {
  	return {
  		
  	}
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: sans-serif;
}
#app {

}
</style>
