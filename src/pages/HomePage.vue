<script>
import ProjectList from "../components/ProjectList.vue";

export default {
  components: { ProjectList },
};
</script>

<template>
  <ProjectList
    title="Most recent"
    class="my-3"
    @changePage="fetchProjects"
  />
</template>

<style lang="scss" scoped></style>
