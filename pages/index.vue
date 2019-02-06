<template>
  <div class="mt-5">
    <div class="container">
      <div class="card-columns">
        <div class="card" v-for="item in allPost" v-bind:key="item.key" @click="openDetail(item)">
          <img class="card-img-top" :src="item.jetpack_featured_media_url+'&w=300'" alt="Card image cap">
          <div class="card-body">
            <p class="card-text"><small class="text-muted">{{ item.date }} - {{ item.status }}</small></p>
            <h5 class="card-title"><span v-html="item.title.rendered"></span></h5>
            <p class="card-text"><small class="text-muted">{{ item.date }}</small></p>
          </div>
        </div>        
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@media (min-width: 768px) {  
  .card-columns {column-count: 3;}
}
/* Large devices (desktops, 992px and up) */
@media (min-width: 992px) { 
 .card-columns {column-count: 3;}
}
 
/* Extra large devices (large desktops, 1200px and up) */
@media (min-width: 1200px) {  
   .card-columns {column-count: 3;} 
}
</style>

<script>
import axios from 'axios'

export default {
  methods : {
    openDetail (data) {
      this.$store.commit('setArticle', data)
      this.$router.replace({ 'path': '/detail' })
    }
  },
  data () {
    return {
      allPost: []
    }
  },
  mounted () {
    axios('https://mariviu.com/wp-json/wp/v2/posts', {
      crossDomain: true
    }).then( response => {
      this.allPost = response.data
    })
  }  
}
</script>