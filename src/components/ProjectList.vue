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
    <div class="row g-4">
      <ProjectCard
        v-for="project in projects"
        :key="project.id"
        :project="project"
        class="col-md-4 d-flex"
      />
    </div>
  </section>
</template>

<style lang="scss" scoped></style>
