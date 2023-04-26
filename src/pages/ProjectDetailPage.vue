<script>
// import ProjectCard from "../components/ProjectCard.vue";

export default {
  name: "ProjectDetailPage",
  //   components: { ProjectCard },

  created() {
    console.log(this.$route.params.id);
  },
};
</script>

<template>
  <h1>Dettaglio Project</h1>
</template>

<style lang="scss" scoped></style>
