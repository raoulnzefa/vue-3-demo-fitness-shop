<template>
  <div v-for="store in stores" :key="store">
    <SingleStore :store="store" />
  </div>
</template>

<script>
import { onMounted, onUnmounted, onUpdated } from "@vue/runtime-core";
import SingleStore from "./SingleStore.vue";
export default {
  name: "StoreCard",
  components: { SingleStore },
  props: ["stores"],
  setup() {
    onMounted(() => console.log("component mounted"));
    onUnmounted(() => console.log("component unmounted"));
    onUpdated(() => console.log("component updated"));
  },
};
</script>

<style></style>
