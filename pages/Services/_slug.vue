<template>
  <v-container fluid>
    <v-row justify="center">
      <v-col cols="12" md="8" lg="6" xl="5">
        <v-sheet>
          <article>
            <v-img :src="article.images" max-height="300"></v-img>
            <h1>{{ article.title }}</h1>
            <v-divider></v-divider>
            <nuxt-content :document="article" />
          </article>
        </v-sheet>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const article = await $content('services', params.slug).fetch()
    return {
      article,
    }
  },
}
</script>
