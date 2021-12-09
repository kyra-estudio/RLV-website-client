<template>
  <div>
    <b-navbar toggleable="md" type="dark" variant="info" class="RLV-nav-bar">
      <b-container class="RLV-bar-container">
        <b-navbar-toggle target="nav_collapse"> </b-navbar-toggle>
        <b-navbar-brand href="./home"
          ><b-img
            :src="require('../static/img/logo/logo-navbar.png')"
            fluid
            class="rlv-logo"
          ></b-img
        ></b-navbar-brand>

        <b-collapse is-nav id="nav_collapse" class="rlv-nav_collapse">
          <b-navbar-nav>
            <b-nav-item @click="goInicio()" class="RLV-navbar-item"
              >Inicio</b-nav-item
            >

            <b-nav-item @click="goRutas()" class="RLV-navbar-item" v-if="noHome"
              >Rutas</b-nav-item
            >
            <b-nav-item
             @click="goActividades()"
              class="RLV-navbar-item"
              v-if="noHome"
              >Actividades</b-nav-item
            >
            <b-nav-item
              @click="goCursosPro()"
              class="RLV-navbar-item"
              v-if="noHome && token"
              >CursosPro</b-nav-item
            >
             <b-nav-item href="./sign-in" class="RLV-navbar-item" v-if="!token"
              >Ingresar</b-nav-item
            >
            <b-nav-item href="./sign-up" class="RLV-navbar-item" v-if="!token"
              >Registro</b-nav-item
            >
          </b-navbar-nav>
          
        </b-collapse>
      </b-container>
      <b-nav-item-dropdown
        id="rlv-avatar"
        class="navbar-right rlv-avatar"
        toggle-class="nav-link-custom"
        right
        v-if="token"
      >
        <template #button-content>
          <span class="mr-auto">Hola {{ name }} </span>
          <b-avatar :src="avatar" size="55px"></b-avatar>
        </template>
        <b-dropdown-item @click="logout()">Logout</b-dropdown-item>
      </b-nav-item-dropdown>
    </b-navbar>
  </div>
</template>

<script>
export default {
  data() {
    return {
      token: '',
      avatar: undefined,
      name:'',
    }
  },
  created() {
    if (process.client) {
      this.token = localStorage.getItem('token')
      this.avatar = localStorage.getItem('avatar')
      this.name = localStorage.getItem('name')
    }
  },
  watch: {
    '$store.state.user.token'(value) {
      if (value) {
        this.token = localStorage.getItem('token')
        this.avatar = localStorage.getItem('avatar')
        this.name = localStorage.getItem('name')
      }
    },
  },
  props: {
    noHome: {
      type: Boolean,
      default: true,
    },
  },
  methods: {
    logout() {
      this.$store.dispatch('user/removeToken')
      this.$router.push('/home')
    },
    goHome() {
      this.$router.push('/home')
    },
    goInicio() {
      this.$router.push('/inicio')
    },
    goRutas() {
      this.$router.push('/rutas')
    },
    goActividades() {
      this.$router.push('/actividades')
    },
    goCursosPro() {
      this.$router.push('/cursos-pro')
    },
  },
}
</script>
