<template>
  <div class="mt-5">
    <div class="container">
      <div class="row justify-content-md-center">
        <div class="col-8">
          <img :src="article.jetpack_featured_media_url+'&w=800'" alt="Card image cap" class="img-fluid">
          <p class="card-text"><small class="text-muted"> {{ article.date }} - {{ article.status }} </small></p>
          <h5 class="card-title"><span v-html="article.title.rendered"></span></h5>
          <p class="card-text img-responsive" v-html="article.content.rendered"></p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  computed: {
    article () { return this.$store.state.article }
  }
}
</script>

<style scoped>

@media (min-width: 768px) {  
    p >>> img {
        width: 100%;
        height: auto;
    }  
}
/* Large devices (desktops, 992px and up) */
@media (min-width: 992px) { 
    p >>> img {
        width: 100%;
        height: auto;
    }
}
 
/* Extra large devices (large desktops, 1200px and up) */
@media (min-width: 1200px) {  
    p >>> img {
        width: 100%;
        height: auto;
    }
}
</style>