<template>
  <header>
    <ul>
      <li v-for="(user, index) in listUser" v-bind:key="index">{{user.email}}</li>
    </ul>
    <h1>
      {{ title }}
      <br />
      <button v-on:click="changeTitleHeader">Thay đổi title từ Component Header</button>
    </h1>
  </header>
</template>

<script>
import ListUser from "./ListUser";
export default {
  name: "comp-header",
  props: {
    title: String,
    listUser: {
      type: Array,
      default: []
    }
  },
  data() {
    return {
      text: "Header"
    };
  },
  components: {
    ListUser
  },
  methods: {
    changeTitleHeader(e) {
      //Khong dc phep thay doi truc tiep
      // Truyen su kien thong bao ra ben ngoai
      // this.title = "Hoc lap trinh front end";
      console.log("Truoc khi kick hoat su kien changeTitleEvent");
      var data = {
        title: "Test => Data truyen thong qua bien event"
      };
      this.$emit("changeTitleEvent", data);
      console.log("Sau khi kick hoat su kien changeTitleEvent");
    }
  }
};
</script>

<style>
</style>
