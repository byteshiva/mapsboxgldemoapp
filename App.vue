<script>
import MapboxMap from "./components/MapboxMap.vue";
import MapboxMarkers from "./components/MapboxMarkers.vue";
import MapboxNavigation from "./components/MapboxNavigation.vue";

export default {
  components: {
    MapboxMap,
    MapboxMarkers,
    MapboxNavigation
  },
  data() {
    return {
      cities: [
        {
          name: "Gemini Flyover",
          lat: "13.0308",
          long: "80.1504"
        },
        {
          name: "Indra Nagar, Adyar",
          lat: "12.5956",
          long: "80.1505"
        },
        {
          name: "Avadi",
          lat: "13.0713",
          long: "80.0636"
        },
        {
          name: "Adyar Bus Depot",
          lat: "12.5950",
          long: "80.1525"
        }
      ]
    };
  }
};
</script>

<template>
  <div id="app">
    <MapboxMap
      access-token="pk.eyJ1IjoiYnl0ZXNoaXZhIiwiYSI6ImNqMWV0bnBlOTAwMGgyeG51ZHI2cDR1MnoifQ.ilOPH7dy5oG_Rg8UcQ6XsA"
    >
      <MapboxMarkers
        :items="cities"
        primary
      >
        <template slot-scope="city">
          {{ city.name }}
        </template>
      </MapboxMarkers>
      <MapboxNavigation/>
    </MapboxMap>
  </div>
</template>

<style lang="scss">
*,
*::before,
*::after {
  box-sizing: content-box;
}

html,
body,
#app {
  height: 100%;
}
</style>
