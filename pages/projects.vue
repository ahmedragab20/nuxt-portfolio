<template>
  <v-container>
    <h3 class="text-center">Not All, just fragment</h3>
    <v-row no-gutters justify="center" align="center" class="mt-5">
      <v-col
        class="text-center"
        cols="12"
        lg="4"
        sm="6"
        v-for="item in projects"
        :key="item.id"
      >
        <ProjectCard :item="item" />
      </v-col>
    </v-row>
  </v-container>
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
