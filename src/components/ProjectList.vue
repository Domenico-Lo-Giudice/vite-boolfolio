<script>
import ProjectCard from "./ProjectCard.vue";

export default {
  props: {
    projects: Array,
    title: String,
  },

  components: { ProjectCard },
};
</script>

<template>
  <section class="container">
    <h1>{{ title }}</h1>
    <ProjectCard
      v-for="project in projects"
      :key="project.id"
      :project="project"
    />
  </section>
</template>

<style lang="scss" scoped></style>
