<script>
import AppHeader from "./components/AppHeader.vue";

export default {
  data() {
    return {
      title: "Hello World",
    };
  },

  components: { AppHeader },
};
</script>

<template>
  <AppHeader />
  <h1>{{ title }}</h1>
</template>

<style lang="scss" scoped></style>
