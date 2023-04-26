<script>
import ProjectCard from "../components/ProjectCard.vue";
import axios from "axios";

export default {
  name: "ProjectDetailPage",

  data() {
    return {
      project: null,
    };
  },
  components: { ProjectCard },

  created() {
    // console.log(this.$route.params.id);

    axios
      .get(`http://127.0.0.1:8000/api/projects/${this.$route.params.id}`)
      .then((response) => {
        this.project = response.data;
      });
  },
};
</script>

<template>
  <ProjectCard
    v-if="project"
    :project="project"
  />
</template>

<style lang="scss" scoped></style>
