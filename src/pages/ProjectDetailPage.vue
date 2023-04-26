<script>
import ProjectCard from "../components/ProjectCard.vue";
import axios from "axios";

export default {
  name: "ProjectDetailPage",

  data() {
    return {
      project: null,
      isLoading: false,
    };
  },
  components: { ProjectCard },

  created() {
    // console.log(this.$route.params.id);
    this.isLoading = true;

    axios
      .get(`http://127.0.0.1:8000/api/projects/${this.$route.params.slug}`)
      .then((response) => {
        // se la chiamata va a buon fine...
        this.project = response.data;
      })
      .catch((err) => {
        // se c'è un errore...
        this.$router.push({ name: "not-found" });
      })
      .finally(() => {
        // comunque sia...
        this.isLoading = false;
      });
  },
};
</script>

<template>
  <AppLoader v-if="isLoading" />
  <h1 class="my-4">Dettaglio Project {{ project?.title }}</h1>
  <ProjectCard
    v-if="project"
    :project="project"
    :isDetail="true"
  />
</template>

<style lang="scss" scoped></style>
