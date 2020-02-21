<template>
  <div id="map">
    <h2>Карта наставников "Промробоквантум"</h2>
    <yandex-map :coords="coords" :zoom="4" @click="onClick">
      <ymap-marker :coords="coords" marker-id="123" hint-content="some hint" />
    </yandex-map>
  </div>
</template>

<style>
#map {
  width: 50%;
  height: 70vh;
}

.ymap-container {
  height: 100%;
}
</style>

<script>
import { yandexMap, ymapMarker } from "vue-yandex-maps";

export default {
  data() {
    return { coords: [54.82896654088406, 39.831893822753904] };
  },
  components: { yandexMap, ymapMarker },
  methods: {
    onClick(e) {
      this.coords = e.get("coords");
    }
  }
};
</script>
