<template>
  <MglMap class="map" :accessToken="accessToken" :mapStyle="mapStyle">
  	<MglMarker :coordinates="coordinates" color="blue" >
  		<v-icon slot="marker">mdi-map-marker</v-icon>
  	</MglMarker>
  </MglMap>
  
</template>

<script>
import Mapbox from "mapbox-gl";
import { MglMap, MglMarker } from "vue-mapbox";

export default {
  name: "mapa",
  components: {
    MglMap,
    MglMarker
  },
  data() {
    return {
      accessToken:
        "pk.eyJ1IjoiYnJhbmRwaW5ndSIsImEiOiJja2gyZHVsenYwMG1xMnZvNHlwaGplc3U4In0.RxD6xt-IussbHBnjQJ24RQ",
      mapStyle: "mapbox://styles/mapbox/streets-v11",
      puntos: [],
      coordinates: [-99.104542, 19.628777]
    };
  },
  created() {
  	//id="lng" value="-99.104542"
  	//id="lat" value="19.628777"
    this.mapbox = Mapbox;
    let spreadSheetId = '1lk6UaqJEHJf_u7CMvOvfFYCVSUyZRQxbrKAhV8i3OQs';
	let testId = '1LmtEnvzGii1aBeAcnwwjxyA9FcXFnH5f0co3hX5uIkI';
	let url = `https://script.google.com/macros/s/AKfycbw_8waQ6ZMQDpjnSF_GsrdIaVncOVKBr9Ld23O2p3_PYncFaIvR/exec?spreadsheetId=${spreadSheetId}&sheet=marcadores`;
	fetch(url)
	.then(res => {
		return res.json()
	})
	.then(data => {
		console.log(data);
		//for(let i in data){
			//this.puntos.push({lng: data[i]["Longitud"], lat: data[i]["Latitud"]});
			//this.puntos.push([-99.104542, 19.628777]);
        //}
	})

  },
  methods: {
  }
};
		
</script>


<style scoped>
.map {
  width: 100%;
  height: 500px;
  
}
.marker{
    background-size: cover;
    width: 50px;
    height: 50px;
    border-radius: 50%;
    cursor: pointer;
    position: relative;
}
.marker::before{
    content: '';
    position: absolute;
    display: block;
    opacity: 0;
    transition: 1s;
    width: 0;
    height: 0;
    border-radius: 20px;
    top: 0;
    left: 0;
    background-color: #fcfcfc;
}

.marker:hover::before{
    opacity: 1;
    width: 200px;
    height: 100px;
    top: -100px;
    left: -75px;
}
</style>