<script lang="ts" setup>
import { onMounted, ref } from "vue";
import { Map, View } from "ol";
import TileLayer from "ol/layer/Tile";
import { OSM } from "ol/source";

const init = () => {
  const map = new Map({
    target: "map",
    layers: [
      new TileLayer({
        source: new OSM(),
      }),
    ],
    view: new View({
      projection: "EPSG:4326",
      center: [114, 22],
      minZoom: 10,
      zoom: 12,
    }),
  });
};

onMounted(() => {
  init();
});
</script>
<template>
  <div id="map"></div>
</template>
<style lang="scss" scoped>
#map {
  width: 100vw;
  height: 100vh;
}
</style>
