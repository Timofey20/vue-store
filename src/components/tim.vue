<template>
  <li>
    {{ index + 1 }}) {{ item.title }} {{ item.age }}
    <button @click="$emit('remove', item.id)">&times;</button>
  </li>
</template>
<script>
export default {
  props: ["item", "index"],
};
</script>
<style lang="scss">
button {
  width: 40px;
  height: 20px;
  background-color: red;
  border-radius: 10px;
}
li {
  display: flex;
  justify-content: space-between;
  margin-bottom: 20px;
  border: 1px solid black;
  padding: 1em 1em;
}
</style>
