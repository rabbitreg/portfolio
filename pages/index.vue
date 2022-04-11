<template>
  <v-container fluids>
    <v-row justify="center">
      <v-card
        v-for="article in blogs"
        :key="article.slug"
        outlined
        max-height="400"
        max-width="300"
        class="ma-10"
        color="#fafafa"
      >
        <nuxt-link :to="'/blogs/' + article.slug">
          <v-img :src="article.images" height="180" width="300"> </v-img>
          <v-card-title>{{ article.title }}</v-card-title>
          <p>{{ article.subtitle }}</p>

          <p>{{ article.date }}</p>
        </nuxt-link>
      </v-card>
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

<style></style>
