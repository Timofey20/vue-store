<template>
  <ul>
    <Tim
      v-for="(item, index) in users"
      :key="index"
      :item="item"
      :index="index"
      v-on:remove="remove"
    ></Tim>
  </ul>
</template>

<script>
import Tim from "./tim.vue";
export default {
  props: ["users"],
  components: {
    Tim,
  },
  methods: {
    remove(id) {
      this.$emit("remove", id);
    },
  },
};
Object;
</script>
