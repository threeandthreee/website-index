<template lang="pug">
v-img(:src="src" :width="width" :height="height")
</template>

<script>
import axios from 'axios'
import jsonpAdapter from 'axios-jsonp'

const url = 'https://blog.3and3.dev/api/read/json'

export default {
  data: () => ({
    src: undefined
  }),
  props: ['width', 'height'],
  async mounted() {
    try {
      let response = await axios.get(url, {adapter: jsonpAdapter})
      this.src = response.data.posts
        .find(it => it.type ==='photo')['photo-url-400']
        .replace(/\\/g, '')
    } catch {
      // nothing
    }
  }
}
</script>