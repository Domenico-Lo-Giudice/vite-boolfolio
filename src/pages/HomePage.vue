<script>
import axios from "axios";
import ProjectList from "../components/ProjectList.vue";

export default {
  data() {
    return {
      projects: {
        list: [],
        pages: [],
      },
    };
  },

  components: { ProjectList },

  emits: ["changePage"],

  methods: {
    fetchProjects(endpoint = null) {
      if (!endpoint) endpoint = "http://127.0.0.1:8000/api/projects";

      axios.get(endpoint).then((response) => {
        this.projects.list = response.data.data;
        this.projects.pages = response.data.links;
      });
    },
  },

  created() {
    this.fetchProjects();
  },
};
</script>

<template>
  <ProjectList
    :projects="projects.list"
    :pages="projects.pages"
    title="Most recent"
    class="my-3"
    @changePage="fetchProjects"
  />
</template>

<style lang="scss" scoped></style>
