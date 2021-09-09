<template>
  <ul>
    <li v-for="content in contents" :key="content.id">
      <!--<nuxt-link :to="`/${content.id}`">-->
        {{ content.title }}
      <!--</nuxt-link>-->
    </li>
  </ul>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData() {
    const { data } = await axios.get(
      // your-service-id部分は自分のサービスidに置き換えてください
      'https://koza-kura.microcms.io/api/v1/blog',
      {
        // your-api-key部分は自分のapi-keyに置き換えてください
        headers: { 'X-API-KEY': 'f62096f1-3b69-446f-8e5d-6f02f0a20f09' }
      }
    )
    return data
  }
}
</script>