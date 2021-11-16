<template>
  <div>
    <b-navbar toggleable="md" type="dark" variant="info" class="RLV-nav-bar">
      <b-container  class="RLV-bar-container">
        <b-navbar-toggle target="nav_collapse"> </b-navbar-toggle>
        <b-navbar-brand href="./home"><b-img :src="require('../static/img/logo/logo-navbar.png')" fluid class="rlv-logo"></b-img></b-navbar-brand>

        <b-collapse is-nav id="nav_collapse" class="rlv-nav_collapse">
          <b-navbar-nav>
            <b-nav-item href="./inicio" class="RLV-navbar-item">Inicio</b-nav-item>
            <b-nav-item href="#" class="RLV-navbar-item">Ingresar</b-nav-item>
            <b-nav-item href="#" class="RLV-navbar-item">Registro</b-nav-item>
            <b-nav-item href="#" class="RLV-navbar-item" v-if="noHome">Rutas</b-nav-item>
          </b-navbar-nav>
        </b-collapse>
      </b-container>
    </b-navbar>
  </div>
</template>

<script>
export default {
  // data() {
  //   return {
  //     token: '',
  //     avatar: undefined,
  //   }
  // },
  // created() {
  //   if (process.client) {
  //     this.token = localStorage.getItem('token')
  //     this.avatar = localStorage.getItem('avatar')
  //   }
  // },
  props: {
    noHome: {
      type: Boolean,
      default: true,
    },
  },
  methods: {
    // logout() {
    //   this.$store.dispatch('user/removeToken')
    //   this.$router.push('/sign-in')
    // },
    goHome() {
      this.$router.push('/home')
    },
  },
}
</script>
