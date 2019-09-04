<template>
  <div class="home">
    <div class="page-header text-center">
      <h1><header>Welcome to Rishi's Routes</header></h1>
    </div>
<!-- MAP SECTION -->
  <section class="clearfix p0">
    <div id="map-canvas"></div>
  </section>


<!-- DIRECTION SECTION -->
    <div class="container">
      <div class="row">
        <div class="col-xs-12 ">
          <div class="bg-search-white">
              <div class="form-group">
                <input type="text" class="form-control" id="exampleInputAddress" placeholder="Enter your Current Location" v-model="currentLocation">
              </div>
              <div class="form-group">
                <input type="text" class="form-control" id="exampleInputAddress" placeholder="Enter your Desired Destination" v-model="destination">
              </div>
              <div class="form-group">
                <button v-on:click="getDirections()" class="btn btn-primary">Search </button>
              </div>
          </div>
        </div>
      </div>
    </div>
    <h3>{{googlemaps['total_time']}}    {{googlemaps['total_distance']}}</h3>
    <div class='form-group'>
      <ul>
        <ul v-for="googlemap,index in googlemaps['steps']">
          {{googlemap}} ({{googlemaps['distance'][index]}}, {{googlemaps['duration'][index]}})
        </ul>
      </ul>
    </div>

<!-- THINGS SECTION -->
    <section class="clearfix thingsArea">
      <div class="container">
        <div class="page-header text-center">
          <h2>Restaurants near your destination <small>These are some of more popular listings</small></h2>
        </div>
        <div class="row">
          <div class="col-md-4 col-sm-6 col-xs-12">
            <div class="thingsBox thinsSpace">
              <div class="thingsImage">
                <img :src="yelp['images'][0]" alt="Image things">
                <div class="thingsMask">
                  <ul class="list-inline rating">
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star-o" aria-hidden="true"></i></li>
                  </ul>
                  <a href="listing-details-right.html"><h2>"{{yelp['names'][0]}}" <i class="fa fa-check-circle" aria-hidden="true"></i></h2></a>
                  <p>{{yelp['address'][0]}}</p>
                  <p>{{yelp['phone'][0]}}</p>
                </div>
              </div>
            </div>
          </div>

          <div class="col-md-4 col-sm-6 col-xs-12">
            <div class="thingsBox thinsSpace">
              <div class="thingsImage">
                <img :src="yelp['images'][1]" alt="Image things">
                <div class="thingsMask">
                  <ul class="list-inline rating">
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                  </ul>
                  <a href="listing-details-right.html"><h2>"{{yelp['names'][1]}}"</h2></a>
                  <p>{{yelp['address'][1]}}</p>
                  <p>{{yelp['phone'][1]}}</p>
                </div>
              </div>
            </div>
          </div>

          <div class="col-md-4 col-sm-6 col-xs-12">
            <div class="thingsBox thinsSpace">
              <div class="thingsImage">
                <img :src="yelp['images'][2]" alt="Image things">
                <div class="thingsMask">
                  <ul class="list-inline rating">
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                  </ul>
                  <a href="listing-details-right.html"><h2>"{{yelp['names'][2]}}"<i class="fa fa-check-circle" aria-hidden="true"></i></h2></a>
                  <p>{{yelp['address'][2]}}</p>
                  <p>{{yelp['phone'][2]}}</p>
                </div>
              </div>
            </div>
          </div>
          <div class="col-md-4 col-sm-6 col-xs-12">
            <div class="thingsBox thinsSpace">
              <div class="thingsImage">
                <img :src="yelp['images'][3]" alt="Image things">
                <div class="thingsMask">
                  <ul class="list-inline rating">
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star-o" aria-hidden="true"></i></li>
                  </ul>
                  <a href="listing-details-right.html"><h2>"{{yelp['names'][3]}}"</h2></a>
                  <p>{{yelp['address'][3]}}</p>
                  <p>{{yelp['phone'][3]}}</p>
                </div>
              </div>
            </div>
          </div>
          <div class="col-md-4 col-sm-6 col-xs-12">
            <div class="thingsBox thinsSpace">
              <div class="thingsImage">
                <img :src="yelp['images'][4]" alt="Image things">
                <div class="thingsMask">
                  <ul class="list-inline rating">
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                  </ul>
                  <a href="listing-details-right.html"><h2>"{{yelp['names'][4]}}"<i class="fa fa-check-circle" aria-hidden="true"></i></h2></a>
                  <p>{{yelp['address'][4]}}</p>
                  <p>{{yelp['phone'][4]}}</p>
                </div>
              </div>
            </div>
          </div>
          <div class="col-md-4 col-sm-6 col-xs-12">
            <div class="thingsBox thinsSpace">
              <div class="thingsImage">
                <img :src="yelp['images'][5]" alt="Image things">
                <div class="thingsMask">
                  <ul class="list-inline rating">
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                  </ul>
                  <a href="listing-details-right.html"><h2>"{{yelp['names'][5]}}"</h2></a>
                  <p>{{yelp['address'][5]}}</p>
                  <p>{{yelp['phone'][5]}}</p>
                </div>
              </div>
            </div>
          </div>
          <div class="col-md-4 col-sm-6 col-xs-12">
            <div class="thingsBox thinsSpace">
              <div class="thingsImage">
                <img :src="yelp['images'][6]" alt="Image things">
                <div class="thingsMask">
                  <ul class="list-inline rating">
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                  </ul>
                  <a href="listing-details-right.html"><h2>"{{yelp['names'][6]}}" <i class="fa fa-check-circle" aria-hidden="true"></i></h2></a>
                  <p>{{yelp['address'][6]}}</p>
                  <p>{{yelp['phone'][6]}}</p>
                </div>
              </div>
            </div>
          </div>
          <div class="col-md-4 col-sm-6 col-xs-12">
            <div class="thingsBox thinsSpace">
              <div class="thingsImage">
                <img :src="yelp['images'][7]" alt="Image things">
                <div class="thingsMask">
                  <ul class="list-inline rating">
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                  </ul>
                  <a href="listing-details-right.html"><h2>"{{yelp['names'][7]}}"</h2></a>
                  <p>{{yelp['address'][7]}}</p>
                  <p>{{yelp['phone'][7]}}</p>
                </div>
              </div>
            </div>
          </div>
          <div class="col-md-4 col-sm-6 col-xs-12">
            <div class="thingsBox thinsSpace">
              <div class="thingsImage">
                <img :src="yelp['images'][8]" alt="Image things">
                <div class="thingsMask">
                  <ul class="list-inline rating">
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                    <li><i class="fa fa-star" aria-hidden="true"></i></li>
                  </ul>
                  <a href="listing-details-right.html"><h2>"{{yelp['names'][8]}}"</h2></a>
                  <p>{{yelp['address'][8]}}</p>
                  <p>{{yelp['phone'][8]}}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

<!-- SERVICES SECTION -->
    <section class="clearfix servicesSection">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <div class="servicesItem">
              <ul class="list-inline listServices">
                <li>
                  <div class="servicesIcon">
                    <i class="icon-listy icon-thermometer-1"></i>
                  </div>
                  <div class="servicesInfo">
                    <h2>Temperature</h2>
                    <p>{{weather["temp_in_fahrenheit"]}}°F</p>
                  </div>
                </li>
                <li>
                  <div class="servicesIcon">
                    <i class="icon-listy icon-rainbow"></i>
                  </div>
                  <div class="servicesInfo">
                    <h2>Description</h2>
                    <p>{{weather["description"]}}</p>
                  </div>
                </li>
                <li>
                  <div class="servicesIcon">
                    <i class="icon-listy icon-temperature"></i>
                  </div>
                  <div class="servicesInfo">
                    <h2>Humidity</h2>
                    <p>{{weather["humidity"]}}%</p>
                  </div>
                </li>
                <li>
                  <div class="servicesIcon">
                    <i class="icon-listy icon-wind-1"></i>
                  </div>
                  <div class="servicesInfo">
                    <h2>Wind Speed</h2>
                    <p>{{weather["windspeed"]}}km/h</p>
                  </div>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </section>
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
      googlemaps: [],
      yelp: {"address": ["", "", "", "", "", "", "", "", ""], "names": ["", "", "", "", "", "", "", "", ""], "images": ["", "", "", "", "", "", "", "", ""], "phone": ["", "", "", "", "", "", "", "", ""]},
      weather: ""
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

      axios.post("/api/googlemaps", newTrip).then(response => {
        console.log(response.data);
        this.googlemaps = response.data;
      });

      axios.post("/api/yelp", newTrip).then(response => {
        console.log(response.data);
        this.yelp = response.data;
      });

      axios.post("/api/weather", newTrip).then(response => {
        console.log(response.data);
        this.weather = response.data;
      });
    }
  }
};
</script>