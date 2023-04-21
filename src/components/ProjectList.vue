<script>
import ProjectCard from "./ProjectCard.vue";

export default {
  props: {
    projects: Array,
  },

  components: { ProjectCard },
};
</script>

<template>
  <ul>
    <ProjectCard
      v-for="project in projects"
      :key="project.id"
      :project="project"
    />
  </ul>
</template>

<style lang="scss" scoped></style>
