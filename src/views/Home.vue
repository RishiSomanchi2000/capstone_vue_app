<template>
  <div class="home">
    <h1>{{ header }}</h1>
    <h4>{{directions}}</h4>
    <p> Current Location: <input type="text" v-model="currentLocation"></p>
    <p> Destination: <input type="text" v-model="destination"></p>
    <button v-on:click="getDirections()"> Find my Route </button>
    <p>{{googlemaps}}</p>
  </div>
</template>

<style>
</style>

<script>
import axios from "axios";
export default {
  data: function() {
    return {
      header: "Welcome to Rishi's Maps!",
      directions: "Enter your current location and desired destination",
      currentLocation: "",
      destination: "",
      googlemaps: []
    };
  },
  created: function() {},
  methods: {
    getDirections: function() {
      console.log('getting directions');
      var newTrip = {
        current_location: this.currentLocation,
        destination: this.destination,
      };

      axios.post("/api/specialdirections", newTrip).then(response => {
        console.log(response.data);
        this.googlemaps.push(response.data);
      });
    }
  }
};
</script>