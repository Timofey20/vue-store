<template>
  <div id="app">
    <EditFiles v-if="editWindowVisible"></EditFiles>
    <AddItem @addPeople="addPeople"></AddItem>
    <Item :users="users" @remove="remove" @edit_form="edit_form"></Item>
  </div>
</template>

<script>
import Item from "./components/Item";
import AddItem from "./components/AddItem";
import EditFiles from "./components/EditFiles";

export default {
  name: "App",
  components: {
    Item,
    AddItem,
    EditFiles,
  },
  data() {
    return {
      users: [
        { id: 1, title: "tim", age: 20 },
        { id: 2, title: "anton", age: 24 },
        { id: 3, title: "elena", age: 55 },
      ],
      editWindowVisible: false,
    };
  },
  methods: {
    remove(id) {
      this.users = this.users.filter((t) => t.id !== id);
    },
    addPeople(item) {
      this.users.push(item);
    },
    edit_form(id) {
      this.editWindowVisible = !this.editWindowVisible;
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
}
.EditFiles {
  position: fixed;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  background-color: rgb(172, 172, 172);
  padding: 2em;
}
.edit_header {
  text-align: center;
}
.edit_back {
  display: flex;
  justify-content: space-between;
  margin-top: 40px;
}
</style>
