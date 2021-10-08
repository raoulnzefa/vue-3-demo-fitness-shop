/* eslint-disable no-unused-vars */
<template>
  <div class="home">
    home
    <input type="text" v-model="search" />
    <p>Search term - {{ search }}</p>
    <div v-for="name in matchingNames" :key="name">{{ name }}</div>
    <button @click="handleClick">Stop watch</button>
  </div>
</template>

<script>
import { computed, ref, watch, watchEffect } from "vue";

export default {
  name: "Home",
  setup() {
    const search = ref("");
    const names = ref(["ngeens", "Ted", "Jeff", "John", "Mwas"]);

    const stopWatch = watch(search, () => {
      console.log("watch function has run");
    });
    const stopWatchEffect = watchEffect(() => {
      console.log("watcheffect", search.value);
    });
    const matchingNames = computed(() => {
      return names.value.filter((name) => name.includes(search.value));
    });
    const handleClick = () => {
      stopWatchEffect();
      stopWatch();
    };
    return { names, search, matchingNames, handleClick };
  },
};
</script>
