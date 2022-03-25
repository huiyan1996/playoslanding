<template>
  <div id="app">
    <div class="container-fluid px-0">
      <navbar />
      <router-view/>
      <customFooter />
    </div>
  </div>
</template>

<script>
import navbar from '@/components/navbar.vue'
import customFooter from '@/components/footer.vue'

export default {
  components: {
    navbar,
    customFooter
  }
}
</script>