<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      app
    >
      <v-list shaped>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" fixed app dense flat>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-btn icon @click.stop="miniVariant = !miniVariant">
        <v-icon>mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn>
      <v-spacer />
      <v-btn fab x-small>
        <img
          src="https://media-exp1.licdn.com/dms/image/C4D03AQEbJq620Yp_BQ/profile-displayphoto-shrink_800_800/0/1635271227369?e=1645056000&v=beta&t=HHdTeq-4IV2rcmt0v_vxAVqESFSxzT5MOtauK8_8D0k"
          width="30"
          class="rounded-circle elevation-5"
          @click="acountList = !acountList"
        />
      </v-btn>
    </v-app-bar>

    <transition name="accounts-list">
      <div class="accounts-list" v-if="acountList">
        <v-card max-width="250" class="mx-auto">
          <img src="@/assets/me.jpg" height="150px" dark />

          <v-list dense nav>
            <v-list-item
              v-for="account in accounts"
              :key="account.to"
              :href="account.to"
              target="_blank"
            >
              <v-list-item-action>
                <v-icon>{{ account.icon }}</v-icon>
              </v-list-item-action>
              <v-list-item-content>
                <v-list-item-title v-text="account.name" />
              </v-list-item-content>
            </v-list-item>
            <v-btn @click="toggleTheme" fab x-small text>
              <v-icon v-if="$vuetify.theme.dark == true"
                >mdi-lightbulb-variant-outline</v-icon
              >
              <v-icon v-else>mdi-weather-night</v-icon>
            </v-btn>
          </v-list>
        </v-card>
      </div>
    </transition>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer :absolute="!fixed" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      drawer: false,
      fixed: false,
      clipped: false,
      miniVariant: false,
      acountList: false,
      title: 'Portfolio',
      items: [
        {
          icon: 'mdi-account',
          title: 'Home',
          to: '/',
        },
        {
          icon: 'mdi-star-four-points-outline',
          title: 'Skills',
          to: '/skills',
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Last Projects',
          to: '/projects',
        },
      ],
      accounts: [
        {
          name: 'gitHub',
          icon: 'mdi-github',
          to: 'https://github.com/ahmedragab20',
        },
        {
          name: 'LinkedIn',
          icon: 'mdi-linkedin',
          to: 'https://www.linkedin.com/in/ahmed-ragab-bb75541b3/',
        },
      ],
    }
  },
  methods: {
    toggleTheme() {
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark
      localStorage.setItem('useDarkTheme', this.$vuetify.theme.dark.toString())
    },
  },
  mounted() {
    const theme = localStorage.getItem('useDarkTheme')
    if (theme) {
      if (theme == 'true') {
        this.$vuetify.theme.dark = true
      } else this.$vuetify.theme.dark = false
    }
  },
}
</script>
<style scoped>
.accounts-list {
  position: fixed;
  top: 8vh;
  right: 15px;
  z-index: 9;
}
/* Transitions */
.accounts-list-enter,
.accounts-list-leave-to {
  transform: translateY(-100px);
  opacity: 0;
}
.accounts-list-enter-active,
.accounts-list-leave-active {
  transition: all 0.3s ease-in-out;
}
.page-enter-active {
  animation: acrossIn 0.45s ease-out both;
}

.page-leave-active {
  animation: acrossOut 0.65s ease-in both;
}

@keyframes acrossIn {
  0% {
    transform: translate3d(-100%, 0, 0);
    opacity: 0.5;
  }
  100% {
    transform: translate3d(0, 0, 0);
    opacity: 1;
  }
}

@keyframes acrossOut {
  0% {
    transform: translate3d(0, 0, 0);
  }
  100% {
    transform: translate3d(100%, 0, 0);
  }
}
@media (max-width: 1024px) {
  @keyframes acrossIn {
    0% {
      transform: translate3d(0, 100%, 0);
      opacity: 0.5;
    }
    100% {
      transform: translate3d(0, 0, 0);
      opacity: 1;
    }
  }

  @keyframes acrossOut {
    0% {
      transform: translate3d(0, 0, 0);
    }
    100% {
      transform: translate3d(0, -100%, 0);
    }
  }
}
</style>
