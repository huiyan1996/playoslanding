<template>
  <div class="row mx-0">
    <div class="col-12 navbar" :class="{home: thisPage=='home'}">
      <div class="container">
        <div class="col-12 d-flex justify-content-end position-relative">
          <router-link to="/" class="logo">
            <img src="@/assets/images/logo.png" alt="logo" width="170px" >
          </router-link>
          <a href="javascript:;" class="burgerBtn" @click="openMenu=!openMenu"><i class="fas fa-bars"></i></a>
          <div class="menuOverlay" v-if="openMenu" @click="openMenu=!openMenu"></div>
          <div class="rightMenu" :class="{open: openMenu}">
            <a href="javascript:;" class="closeBtn" @click="openMenu=!openMenu"><i class="fas fa-times"></i></a>

            <router-link to="/" class="menuItem">Home</router-link>
            <router-link to="/news" class="menuItem">News</router-link>
            <router-link to="/shop" class="menuItem inactive">Shop</router-link>

            <a href="#" class="socialIcon twitter"><i class="fab fa-twitter"></i></a>
            <a href="#" class="socialIcon instagram"><i class="fab fa-instagram"></i></a>
            <a href="#" class="socialIcon discord"><i class="fab fa-discord"></i></a>
            <a href="#" class="socialIcon"><img src="@/assets/images/opensea.png" width="100%"></a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Navbar',
  data: function () {
    return {
      openMenu: false
    }
  },
  computed: {
    thisPage() {
        return this.$route.name;
    }
}
}
</script>