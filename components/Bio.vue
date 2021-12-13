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
      <img
        :aspect-ratio="4 / 4"
        :width="width"
        class="rounded-circle"
        src="https://media-exp1.licdn.com/dms/image/C4D03AQEbJq620Yp_BQ/profile-displayphoto-shrink_800_800/0/1635271227369?e=1645056000&v=beta&t=HHdTeq-4IV2rcmt0v_vxAVqESFSxzT5MOtauK8_8D0k"
      />
    </div>
    <h5 class="mt-7 text-center grey--text accent-4 body-2">
      Hello, I'm Ahmed Ragab working as a Front-end web Developer with a year of
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
