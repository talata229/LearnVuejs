<template>
  <div id="app">
    <div class="container">
      <button v-on:click="title ='Học lập trình Vuejs'">Thay doi title tu Component App.vue</button>
      <comp-header
        v-bind:title="title"
        v-on:changeTitleEvent="handleChangeTitle"
        v-bind:listUser="listUser"
      />
      <list-user v-bind:listUser="listUser" v-on:deleteUserEvent="handleDeleteUser" />
      <comp-footer v-bind:title="title" />
      <demo-ref></demo-ref>
    </div>
  </div>
</template>

<script>
import DemoRef from "./components/DemoRef";
import CompHeader from "./components/CompHeader.vue";
import CompFooter from "./components/CompFooter.vue";
import ListUser from "./components/ListUser.vue";
export default {
  name: "app",
  data() {
    return {
      title: "Hello vue js - Header...",
      listUser: [
        { id: 100, email: "test1@gmail.com", active: true },
        { id: 101, email: "test2@gmail.com", active: false },
        { id: 102, email: "test3@gmail.com", active: true },
        { id: 103, email: "test4@gmail.com", active: true },
        { id: 104, email: "test5@gmail.com", active: false },
        { id: 105, email: "test6@gmail.com", active: true }
      ]
    };
  },
  components: {
    CompHeader,
    CompFooter,
    ListUser,
    DemoRef
  },
  methods: {
    handleChangeTitle(data) {
      this.title = data.title;
      console.log("Handle change title App.vue", data);
    },
    handleDeleteUser(data) {
      console.log("App", data);
      this.listUser = this.listUser.filter(user => user.id !== data);
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.container {
  max-width: 1170px;
  margin: 0 auto;
  padding: 0 15px;
  min-height: 3000px;
}
</style>
