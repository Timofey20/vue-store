<template>
  <div>
    <input type="text" v-model="item" />
    <input type="text" v-model="age" />
    <button @click="addPeople">Add</button>
  </div>
</template>
<script>
export default {
  props: [],
  data() {
    return {
      item: "",
      age: "",
    };
  },
  methods: {
    addPeople() {
      if (this.item.trim()) {
        const guys = {
          id: Date.now(),
          title: this.item,
          age: this.age,
        };
        this.$emit("addPeople", guys);
      }
    },
  },
};
</script>
