<template>
  <div class="home">
    home
    <StoreCard v-if="showStores" :stores="stores" />
    <button @click="showStores = !showStores">Toggle Stores</button>
    <button @click="stores.pop()">Delete a Store</button>
  </div>
</template>

<script>
import { ref } from "vue";
import StoreCard from "../components/Stores/Card.vue";
export default {
  name: "Home",
  components: { StoreCard },
  setup() {
    const stores = ref([
      { name: "General shop", owner: "Ngeene" },
      { name: "John D General shop", owner: "kori" },
    ]);
    const showStores = ref(true);
    return { stores, showStores };
  },
};
</script>
