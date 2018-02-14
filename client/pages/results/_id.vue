<template lang="html">
  <div class="idValue">
    <h1>Hello from the route of {{$route.params.id}}</h1>
    {{albumData}}
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data () {
    albumData: []
  },
  asyncData({ params }) {
    return axios.get(`https://itunes.apple.com/search?term=${params.id}&entityalbum`)
      .then((response) => {
        return {albumData: response.data.results}
      })
  }
  // middleware: 'search' //want to use a store? go ahead and uncomment this 
}
</script>

<style lang="css">
</style>
