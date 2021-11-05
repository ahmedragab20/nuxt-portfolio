<template>
  <v-row>
    <v-col
      class="text-center"
      cols="12"
      xs="12"
      sm="6"
      v-for="item in projects"
      :key="item.id"
    >
      <ProjectCard :item="item" />
    </v-col>
  </v-row>
</template>
<script>
import projects from '~/data/projects'
export default {
  head: {
    title: 'Last Projects',
  },
  data() {
    return {
      projects,
    }
  },
}
</script>
