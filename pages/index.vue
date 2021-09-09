<template>
  <ul>
    <li v-for="content in contents" :key="content.id">
      <nuxt-link :to="`/${content.id}`">
        {{ content.title }}
      </nuxt-link>
    </li>
  </ul>
</template>

<script>
import axios from 'axios';
export default{
  async asyncData({ $config }) {
    const { data } = await axios.get(
      
      'https://koza-kura.microcms.io/api/v1/blog',
      {
        
        headers: { 'X-API-KEY': $config.apiKey}
      }
    )
    return data
  }
}
</script>


<style scoped>
li{
  font-size: 12px;
  letter-spacing: 0.2em;
  list-style-type: none;
  padding: 3px;
}
a{
  text-decoration: none;
  color:green;

}
</style>