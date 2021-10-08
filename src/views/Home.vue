<template>
  <div class="home">
    home
    <h3>Refs</h3>
    <p>My name is {{ user.name }} and my age is {{ user.age }}</p>
    <button @click="updateUser">Update User 1</button>
    <h3>Reactive</h3>
    <p>My name is {{ user2.name }} and my age is {{ user2.age }}</p>
    <button @click="updateUser2">Update User 2</button>
  </div>
</template>

<script>
import { ref, reactive } from "@vue/reactivity";
export default {
  name: "Home",
  setup() {
    // const name = ref("Ted");
    // const age = ref(30);
    const user = ref({ name: "Lewis", age: 25 });
    const user2 = reactive({ name: "John", age: 15 });
    const updateUser = () => {
      user.value.name = "Lewis";
      user.value.age = "39";
    };
    const updateUser2 = () => {
      user2.name = "Lawrence";
      user2.age = "23";
    };
    return { user, user2, updateUser, updateUser2 };
  },
};
</script>
