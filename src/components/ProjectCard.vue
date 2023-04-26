<script>
export default {
  name: "ProjectCard",

  props: {
    project: Object,
    isDetail: Boolean,
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
      <div class="card-header clearfix">
        <span
          v-if="project.type"
          class="badge float-end"
          >{{ project.type.label }}
        </span>
        <h2>{{ project.title }}</h2>
      </div>
      <div class="card-body">
        <div v-if="project.teches.length">
          <span
            v-for="teche in project.teches"
            :key="teche.id"
            class="badge rounded-pill me-2"
            :style="{ backgroundColor: teche.color }"
          >
            {{ teche.label }}
          </span>
          <hr />
        </div>

        {{ isDetail ? project.text : abstract }}
      </div>
      <div class="card-footer d-flex justify-content-between">
        Created at {{ project.created_at }}
        <router-link
          v-if="!isDetail"
          class="btn btn-primary btn-sm"
          :to="{
            name: 'project-detail',
            params: {
              slug: project.slug,
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
