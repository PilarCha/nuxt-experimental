<template lang="html">
  <div class="idValue">
    <h1>Results For {{$route.params.id}}</h1>
    <div class="" v-if="albumExists">
      <div v-for="(album,index) in albumData">
        <box
          :title="album.collectionCensoredName"
          :image="album.artworkUrl100"
          :artistname="album.artistname"
          :url="album.artistViewUrl"
          :color="colorPicker(index)"
        />
      </div>
    </div>
    <div class="" v-else>
      <h1>Nothing Came Back Possible Misspell</h1>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import box from '@/components/box.vue'
export default {
  data () {
    albumData: []
  },
  methods: {
    colorPicker(index) {
      return index % 2 == 0 ? 'red' : 'blue'
    }
  },
  computed: {
    albumExists() {
      return this.albumData.length > 0
    }
  },
  components: {
    box
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
