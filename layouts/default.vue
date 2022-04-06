<template>
  <v-app dark>
    <v-main>
      <Nuxt />
    </v-main>

    <v-footer :absolute="!fixed" id="footer" app>
      <span>&copy; {{ new Date().getFullYear() }}-{{ title }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/',
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire',
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'MICHIKUSA',
    }
  },
}
</script>
<style>
#appbar {
  background-color: #dfcba5;
}
#footer {
  background-color: #dfcba5;
}
#footer span {
  margin: auto;
  padding: auto;
  text-align: center;
  color: black;
}
.header-title-link {
  text-decoration: none;
}
</style>
