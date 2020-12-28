<template>
  <div id="app">
    <AddItem @addPeople="addPeople"></AddItem>
    <Item :users="users" @remove="remove"></Item>
  </div>
</template>

<script>
import Item from "./components/Item";
import AddItem from "./components/AddItem";

export default {
  name: "App",
  components: {
    Item,
    AddItem,
  },
  data() {
    return {
      users: [
        { id: 1, title: "tim", age: 20 },
        { id: 2, title: "anton", age: 24 },
        { id: 3, title: "elena", age: 55 },
      ],
    };
  },
  methods: {
    remove(id) {
      this.users = this.users.filter((t) => t.id !== id);
    },
    addPeople(item) {
      console.log(item);
      this.users.push(item);
    },
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  margin-left: 50px;
}
</style>
