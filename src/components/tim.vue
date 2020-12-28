<template>
  <li>
    {{ index + 1 }}) {{ item.title }} {{ item.age }}
    <button @click="$emit('edit_form', item.id)">Edit files</button>

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
  background-color: red;
  border-radius: 10px;
  padding: 1em;
  color: white;
  font-weight: 600;
}
li {
  display: flex;
  justify-content: space-between;
  margin-bottom: 20px;
  border: 1px solid black;
  padding: 1em 1em;
}
</style>
