<template>
  <footer>
    <h1>{{ title }}</h1>
  </footer>
</template>

<script>
export default {
  name: "comp-footer",
  props: {
    title: {
      type: String,
      default: "Gia tri mac dinh khi khong truyen"
    }
  },
  data() {
    return {
      textFooter: "Hello Footer"
    };
  }
};
</script>

<style>
</style>
