<template>
  <div id="app">
    <div class="container-fluid px-0">
      <navbar />
      <router-view/>
    </div>
  </div>
</template>

<script>
import navbar from '@/components/navbar.vue'
export default {
  components: {
    navbar
  }
}
</script>