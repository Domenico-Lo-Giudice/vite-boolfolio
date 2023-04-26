<script>
import AppHeader from "./components/AppHeader.vue";
import HomePage from "./pages/HomePage.vue";

export default {
  data() {
    return {
      title: "Vue Boolfolio",
    };
  },

  components: { AppHeader, HomePage },
};
</script>

<template>
  <AppHeader :title="title" />

  <!-- todo: inserire router component -->

  <HomePage />
</template>

<style lang="scss" scoped></style>
