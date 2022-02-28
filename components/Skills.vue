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
              class="grey lighten-4"
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
}
</script>

<style scoped>
/* .skill-card {
  position: relative !important;
}
.skill-card .v-card__title {
  position: absolute !important;
  bottom: 0 !important;
}
@media (max-width: 480px) {
  .skill-card {
    max-width: 150px !important;
    min-height: 220px !important;
  }
  .v-card__title {
    font-size: 1rem !important;
    padding: 0 !important;
  }
}
@media (max-width: 320px) {
  .skill-card {
    max-width: 110px !important;
    min-height: 155px !important;
  }
  .v-card__title {
    font-size: 0.75rem !important;
  }
} */
</style>
