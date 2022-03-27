<template>
  <div class="bio d-flex flex-column justify-space-between align-center">
    <v-slider
      v-model="width"
      class="align-self-stretch"
      color="grey"
      min="200"
      max="400"
      step="1"
    ></v-slider>

    <div class="image overflow-hidden elevation-20 rounded-circle">
      <v-img
        :aspect-ratio="4 / 4"
        :width="width"
        class="rounded-circle"
        :src="img"
      ></v-img>
    </div>
    <h5 class="mt-7 text-center grey--text accent-4 body-2">
      Hi, I'm Ahmed Ragab working as a Front-end web Developer with a year of
      experience. I've worked on more than 25 projects using Vue.js, Nuxt.js,
      and some other different technologies; you can try some of them from
      <nuxt-link to="/projects" class="grey--text">here</nuxt-link>.
    </h5>
  </div>
</template>

<script>
export default {
  data() {
    return {
      width: 200,
      img: require('@/assets/me.jpg'),
      width: 100,
    }
  },
}
</script>

<style lang="scss" scoped>
.image {
  img {
    object-fit: cover;
  }
}
</style>
