<template>
  <v-container fluids>
    <v-row justify="center">
      <h1 align="center" class="mt-6">{{ title }}</h1>
      <v-card max-width="1400" class="ma-10">
        <v-row justify="center">
          <v-card
            v-for="article in blogs"
            :key="article.slug"
            outlined
            max-height="400"
            max-width="250"
            class="ma-10"
            color="#fafafa"
          >
            <nuxt-link :to="'/blogs/' + article.slug" class="linktitle">
              <v-img :src="article.images" height="180" width="300"> </v-img>
              <h3>{{ article.title }}</h3>
              <p>{{ article.subtitle }}</p>

              <p>{{ article.date }}</p>
            </nuxt-link>
            <v-chip
              small
              class="ma-2 mt-0"
              v-if="selectTag"
              close
              @click:close="resetTag()"
            >
              {{ selectTag }}
            </v-chip>
          </v-card>
        </v-row>
      </v-card>
    </v-row>
  </v-container>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const blogs = await $content('blogs').sortBy('createdAt', 'desc').fetch()

    return {
      title: '記事一覧',
      blogs,
    }
  },
}
</script>

<style>
.v-application a.linktitle {
  color: black;
}
</style>
