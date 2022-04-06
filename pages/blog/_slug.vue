<template>
  <artcile>
    <h1>{{ article.title }}</h1>
    <NuxtContent :document="article" />
  </artcile>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const article = await $content('blog', params.slug).fetch()
    return {
      article,
    }
  },
}
</script>
