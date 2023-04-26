<script>
import AppHeader from "./components/AppHeader.vue";

export default {
  data() {
    return {
      title: "Vue Boolfolio",
    };
  },

  components: { AppHeader },
};
</script>

<template>
  <AppHeader :title="title" />

  <router-view></router-view>
</template>

<style lang="scss" scoped></style>
