<template>
  <v-container>
    <v-row align="center">
      <v-col cols="12" md="9" lg="6" xl="5">
        <v-card
          v-for="article in blogs"
          :key="article.slug"
          outlined
          width="200"
        >
          <nuxt-link :to="'/blogs/' + article.slug">
            <v-card-title class="justify-center">{{
              article.title
            }}</v-card-title>
            <p class="text-center">{{ article.subtitle }}</p>
            <p>{{ article.date }}</p>
          </nuxt-link>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const blogs = await $content('blogs').sortBy('createdAt', 'desc').fetch()
    return {
      blogs,
    }
  },
}
</script>
