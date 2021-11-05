<template>
  <div class="project-card">
    <v-container>
      <v-card class="mx-auto" max-width="400" elevation="10" shaped>
        <v-img height="200px" :src="item.img"> </v-img>

        <div
          class="v-text d-flex justify-start align-start flex-column px-4 py-2"
        >
          <p class="subtitle-2 grey--text">{{ item.used }}</p>
          <h3 class="body-1">{{ item.name }}</h3>
        </div>

        <v-card-actions>
          <v-btn
            color="teal accent-4"
            text
            rounded
            dark
            :href="item.url"
            target="_blank"
          >
            Live Preview <v-icon right small>mdi-share-all-outline</v-icon>
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-container>
  </div>
</template>

<script>
export default {
  props: ['item'],
  data() {
    return {}
  },
}
</script>

<style scoped>
.project-card img {
  mix-blend-mode: multiply !important;
}
</style>
