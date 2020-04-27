<template>
  <div class="user">
    <h2>{{user.email}}</h2>
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
  }
};
</script>

<style>
</style>