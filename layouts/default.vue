<template>
  <v-app dark>
    <v-app-bar :clipped-right="clipped" id="appbar" dense fixed flat app>
      <v-toolbar-title>
        <nuxt-link to="/" class="header-title-link">
          <h3>{{ title }}</h3>
        </nuxt-link>
      </v-toolbar-title>
      <v-spacer></v-spacer>
    </v-app-bar>
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
  background-color: #fafafa;
}
#footer {
  background-color: #fafafa;
  margin-top: auto;
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
.v-application a.header-title-link {
  color: #000;
}
</style>
