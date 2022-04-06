<template>
  <ul>
    <li v-for="article in blog" :key="article.slug">
      <nuxt-link :to="'/blog/' + article.slug">
        <time :datetime="article.createdAt">
          {{ $dateFns.format(newDate(article.createdAt), 'yyyy/MM/dd') }}
        </time>
        <p>{{ article.title }}</p>
      </nuxt-link>
    </li>
  </ul>
</template>

<script>
export default {
  async asyncDate({ $content }) {
    const blog = await $content('blog').sortBy('createdAt', 'desc').fetch()
    return {
      blog,
    }
  },
}
</script>
