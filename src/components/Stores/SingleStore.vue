<template>
  <div></div>
  <h3>Name of store is {{ store.name }} owned by {{ snippet }}</h3>
</template>

<script>
import { computed } from "@vue/reactivity";
export default {
  name: "SingleStore",
  props: ["store"],
  setup(props) {
    const snippet = computed(() => {
      return props.store.owner.substring(0, 5) + "...";
    });

    return { snippet };
  },
};
</script>

<style></style>
