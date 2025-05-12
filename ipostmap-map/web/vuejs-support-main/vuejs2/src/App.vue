<template>
  <div style="width: 80%; height: 600px" id="app">
    <Map4dMap @onMapReady="onMapReady" :options="options1" :id="id" version="2.4"
      accessKey="__YOUR_KEY___" />
    <!-- <Map4dMap :options="options2" id="map4" version="2.4" accessKey="__YOUR_KEY___"/> -->
  </div>
</template>

<script>
import Map4dMap from './components/Map4dMap.vue'

export default {
  name: 'app',
  components: {
    Map4dMap
  },
  data() {
    // Do not set the value used to perform the event with the map here, it will generate REACTIVE values. Ex: annotation (marker, circle, ..)
    // Because if placed in data, it will use vuejs' reactive mechanism, affecting the rendering speed of the map
    // Please put external data, declare in created() using to save values
    return {
      options1: {
        center: { lat: 16.072163491469226, lng: 108.22690536081757 },
        zoom: 17,
        controls: false
      },
      options2: {
        center: { lat: 16.072163491469226, lng: 108.22690536081757 },
        zoom: 18,
        controls: true
      },
      id: "map3",
      // EX: declare reactive value in map - should not be used
      circle: null,
    }
  },
  created() {
    // Ex: SHOULD declare interactive value with map here. Ex: mapMarkers, locations
    this.mapMarkers = [],
    this.locations = [
      { lat: 16.0724418472019, lng: 108.22477300599348 },
      { lat: 16.07206555139652, lng: 108.2253469983612 },
      { lat: 16.07097789787369, lng: 108.22504659114071 },
    ]
  },
  methods: {
    onMapReady(map, id) {
      console.log(`Map with id: ${id} is ready`)
      //TODO: Map interaction from here      

      let map4d = window.map4d //remove if disable no-undef from eslint

      let centerMap = map.getCamera().getTarget()

      // START NOT using REACTIVE value 
      this.circle = new map4d.Circle({
        center: centerMap,
        radius: 50,
        strokeWidth: 1.0,
      })
      this.circle.setMap(map)
      // END NOT using REACTIVE value here 

      // START SHOULD using NON-REACTIVE value
      // Add 1 marker to the map
      let marker = new map4d.Marker({
        position: centerMap,
        anchor: [0.5, 1.0],
        draggable: true,
        label: new map4d.MarkerLabel({ text: "Demo Marker", color: "FF00FF", fontSize: 12 })
      })
      marker.setMap(map)

      // More markers
      for (let i = 0; i < this.locations.length; i++) {
        const marker = new map4d.Marker({
          position: this.locations[i],
          anchor: [0.5, 1.0],
          draggable: true,
        });
        marker.setMap(map)    
        this.mapMarkers.push(marker);
      }

      // Add mouseOut event of marker
      map.addListener("mouseOut", (args) => {
        console.log("Marker mouseout", args);
        this.removeMarkers();
      }, {marker: true});
      // END SHOULD using NON-REACTIVE value

    },
    removeMarkers() {
      for (let i = 0; i < this.mapMarkers.length; i++) {
        this.mapMarkers[i].setMap(null);
      }
      this.mapMarkers = [];
    },
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 20px;
}
</style>
