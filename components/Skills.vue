<template>
  <div class="skills">
    <v-container>
      <v-row justify="center" align="center">
        <v-flex xs6 md3 lg2 v-for="item in skills" :key="item.id">
          <v-card
            max-width="200px"
            min-height="220px"
            class="ma-4 skill-card"
            outlined
          >
            <div class="pa-2">
              <v-img
                :src="item.img"
                contain
                height="160"
                class="rounded"
              ></v-img>
            </div>
            <v-card-title
              v-text="item.name"
              :class="isDark ? 'grey darken-4' : 'grey lighten-4'"
            ></v-card-title>
          </v-card>
        </v-flex>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import skills from '@/data/skills'
export default {
  data() {
    return {
      skills,
    }
  },
  computed: {
    isDark() {
      return this.$vuetify.theme.dark
    },
  },
}
</script>