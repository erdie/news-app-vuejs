<template>
  <div>
    <!-- Navigation -->
    <Navigation/>
    <!-- Content -->
    <div class="container content">
      <!-- Content -->
      <nuxt/>
    </div>
    <!-- Footer -->
    <div class="footer">
      Copyright &copy; 2019 Mariviu. All Rights Reserved
    </div>
  </div>
</template>

<script>
import Navigation from '~/components/navigation.vue'
import Banner from '~/components/banner.vue'

export default {
  components: {
    Navigation,
    Banner
  }
}
</script>