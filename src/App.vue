<script>
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";
import ProjectList from "./components/ProjectList.vue";

export default {
  data() {
    return {
      title: "Vue Boolfolio",
      projects: [],
    };
  },

  components: { AppHeader, ProjectList },

  methods: {
    fetchProjects() {
      axios.get("http://127.0.0.1:8000/api/projects").then((response) => {
        this.projects = response.data;
      });
    },
  },

  created() {
    this.fetchProjects();
  },
};
</script>

<template>
  <AppHeader :title="title" />
  <ProjectList
    :projects="projects"
    title="Most recent"
    class="my-3"
  />
</template>

<style lang="scss" scoped></style>
