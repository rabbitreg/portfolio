<template>
  <v-container fluid>
    <v-row justify="center">
      <v-col cols="12" md="8" lg="6" xl="5">
        <article>
          <v-sheet>
            <v-img :src="article.images" max-height="550"></v-img>
            <h1>{{ article.title }}</h1>
            <p>{{ article.date }}</p>
            <v-divider></v-divider>
            <nuxt-content :document="article" />
          </v-sheet>
        </article>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const article = await $content('blogs', params.slug).fetch()
    return {
      article,
    }
  },
}
</script>
