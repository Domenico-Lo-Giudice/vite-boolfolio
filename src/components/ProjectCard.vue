<script>
export default {
  name: "ProjectCard",

  props: {
    project: Object,
  },
};
</script>

<template>
  <li>{{ project.title }}</li>
</template>

<style lang="scss" scoped></style>
