<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-12 px-0 bannerWrapper" v-in-viewport>
        <img src="@/assets/images/banner.png" width="100%" alt="">
      </div>
    </div>
    <div class="row">
      <div class="col-12 px-0">
        <div class="progress-wrapper">
          <div class="progress-bar progress-bar-width" data-progress-bar-percent="100">
            <div class="progress-bar-anim"></div>
          </div>
        </div>
      </div>
    </div>
    <div class="row siteDescWrapper">
      <div class="col-12">
        <div class="container siteDesc">
          <div class="row">
            <div class="col-md-6 col-lg-4 descriptionWrapper" v-in-viewport.once='{ margin: "-50% 0%" }'>
              <p class="">Leave the drab reality and enter the world of PlayOS. It’s a magical space where colors reign supreme and everyone just wants to have fun. Give it a spin and see which one of our personas you get.</p>
            </div>
            <div class="col-md-6 col-lg-4 descriptionWrapper" v-in-viewport.once='{ margin: "-50% 0%" }'>
              <p class="">These personas are your ticket into the playground with the coolest crew in town. More NFTs to drop. More mediums to come. It is a brave new digital world. Come over and play.</p>
            </div>
          </div>
          <div class="roadMapIcon">
            <img src="@/assets/images/roadmap.png" width="100%" alt="">
          </div>
          <div class="row justify-content-center">
            <div class="col-md-6">
              <video width="100%" controls>
                <source src="@/assets/images/nft.mp4" type="video/mp4">
                Your browser does not support the video tag.
              </video>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col-12 px-0">
        <div class="progress-wrapper">
          <div class="progress-bar progress-bar-width" data-progress-bar-percent="100">
            <div class="progress-bar-anim"></div>
          </div>
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col-12 px-0 bannerWrapper" v-in-viewport='{ margin: "-20% 0%" }'>
        <img src="@/assets/images/banner.png" width="100%" alt="">
      </div>
    </div>
    <customFooter />

    <transition name='fade'>
      <div class="splashScreen" v-if="showSplash">
        <img class="splashLogo" src="@/assets/images/logo.png" alt="logo" width="170px" >
      </div>
    </transition>
  </div>
</template>

<script>
// @ is an alias to /src
import customFooter from '@/components/footer.vue'

export default {
  name: 'Home',
  components: {
    customFooter
  },
  data: function() {
    return {
      showSplash: true
    }
  },
  mounted: function() {
    var self = this
    if(localStorage.getItem('doneLoad') == 1) {
      self.showSplash = false
    }else {
      setTimeout(function() {
        self.showSplash = false
        localStorage.setItem('doneLoad', 1)
      }, 5000)
    }
  }
}
</script>

<style>
  .fade-enter-active {
    transition: all .3s ease;
  }
  .fade-leave-active {
    transition: all .3s cubic-bezier(1.0, 0.5, 0.8, 1.0);
  }
  .fade-enter, .fade-leave-to {
    opacity: 0;
  }  
</style>