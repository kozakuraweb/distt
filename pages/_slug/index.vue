<template>
  <main class="main">
    <h1 class="title">{{ title }}</h1>
    <p class="publishedAt">{{ publishedAt }}</p>
    <div class="post" v-html="body"></div>
  </main>
</template>


<script>
import axios from 'axios'

export default {
  async asyncData({ params }) {
    const { data } = await axios.get(
      `https://koza-kura.microcms.io/api/v1/blog/${params.slug}`,
      {
        headers: { 'X-API-KEY': 'f62096f1-3b69-446f-8e5d-6f02f0a20f09' }
      }
    )
    return data
  }
}
</script>や

