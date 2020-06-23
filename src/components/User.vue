<template>
  <div class="user">
    <h3>{{user.email}}</h3>
    <button class="delete" v-on:click="handleDelete">Delete</button>
  </div>
</template>

<script>
export default {
  name: "user",
  props: {
    user: {
      type: Object,
      default: {}
    }
  },
  data() {
    return {};
  },
  methods: {
    handleDelete(e) {
      this.$emit("deleteUser", this.user.id);
    }
  }
};
</script>

<style>
.user {
  position: relative;
}
.user .delete {
  position: absolute;
  top: 0;
  right: 0;
}
</style>