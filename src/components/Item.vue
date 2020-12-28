<template>
  <ul>
    <Tim
      v-for="(item, index) in users"
      :key="index"
      :item="item"
      :index="index"
      v-on:remove="remove"
      @edit_form="edit_form"
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
    edit_form(id) {
      this.$emit("edit_form", id);
    },
  },
};
Object;
</script>
