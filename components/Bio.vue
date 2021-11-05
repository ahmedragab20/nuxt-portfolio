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
        max-width="400"
        max-height="400"
        class="rounded-circle"
        src="https://scontent.fcai20-3.fna.fbcdn.net/v/t1.6435-9/250896130_268140081905482_6565534344556685289_n.jpg?_nc_cat=107&ccb=1-5&_nc_sid=09cbfe&_nc_eui2=AeHjPk8ImlGm0WUWnga_xCSsvqtH4_Plgr--q0fj8-WCv8nUrqoiaVtloSMnv7m-n2TbSHEOfS9_Eb4mD6ktS093&_nc_ohc=XgtEwc1GbGkAX-KvrMt&_nc_ht=scontent.fcai20-3.fna&oh=bd232fbdca1a1ad100eadfd02c65d333&oe=61AB3C37"
      ></v-img>
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
      width: 200,
    }
  },
}
</script>

<style lang="scss" scoped></style>
