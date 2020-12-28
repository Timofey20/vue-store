<template>
  <div class="EditFiles">
    <div class="edit_header">
      <h4>Change</h4>
    </div>
    <div class="edit_input">
      <div class="edit_input_name">
        Введите имя
        <input type="text" v-model="name" />
      </div>
      <div class="edit_input_name">
        Введите возраст
        <input type="text" v-model="age" />
      </div>
    </div>
    <div class="edit_back">
      <button @click="returnBack">Back</button>
      <button @click="sumbitChange">Sumbit</button>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      name: "",
      age: "",
    };
  },
};
</script>
<style lang="scss"></style>
