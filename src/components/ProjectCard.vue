<script>
export default {
  name: "ProjectCard",

  props: {
    project: Object,
  },

  computed: {
    abstract() {
      return this.project.text.slice(0, 200) + "...";
    },
  },
};
</script>

<template>
  <div>
    <div class="card">
      <div class="card-header">
        <h2>{{ project.title }}</h2>
      </div>
      <div class="card-body">
        {{ project.text }}
      </div>
      <div class="card-footer d-flex justify-content-between">
        Created at {{ project.created_at }}
        <router-link
          class="btn btn-primary btn-sm"
          :to="{
            name: 'project-detail',
            params: {
              id: project.id,
            },
          }"
        >
          Vedi
        </router-link>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
