<template>
  <div class="rlv-orientacion">
    <div class="rlv-subnav">
      <b-nav>
        <b-nav-item @click="onOrientacion()" class="rlv-subnav-item" 
          >Curso Orientación</b-nav-item
        >
        <b-nav-item @click="onSenderismo()" class="rlv-subnav-item" active
          >Senderismo</b-nav-item
        >
        <b-nav-item @click="onAventuras()" class="rlv-subnav-item"
          >Aventuras
        </b-nav-item>
        <b-nav-item @click="onMicologia()" class="rlv-subnav-item"
          >Curso de Micología
        </b-nav-item>
      </b-nav>
    </div>
    <b-container class="rlv-cursos-container mt-5">
      <b-row>
        <b-col cols="12" md="12" lg="6">
          <b-row>
            <b-col cols="3"></b-col>
            <b-col cols="3">
              <div class="img-actividades text-right">
                <b-img
                  :src="require('../static/img/iconos/i-senderismo.png')"
                  fluid
                ></b-img>
              </div>
            </b-col>
            <b-col cols="4">
              <h1 class="rlv-title-cursos">Senderismo</h1>
              <p class="rlv-text-cursos">
                Apuntarse a las actividades implica la aceptación de las
                condiciones y normas de funcionamiento del club.
              </p>
              <p class="rlv-text-cursos">
                Descubre las mejores rutas de senderismo en Madrid y alrededores. ¡No te pierdas la próximas actividades! 
              </p>
              <p class="rlv-text-cursos">
                Rutas de iniciación. Rutas de nivel avanzado. Tipos: Ruta y raquetas de nieve, Senderismo en Madrid, Nuevas actividades.
              </p>
            </b-col>
            <b-col cols="2"></b-col>
          </b-row>
        </b-col>
        <b-col cols="12" md="12" lg="6">
          <div class="img-actividades d-flex justify-content-center">
            
            <b-img
              :src="require('../static/img/actividades/senderismo.png')"
              fluid
            ></b-img>
            <div class="rlv-btn-actividades-pst">
              <div class="rlv-btn-actividades" @click="onSignUp()" v-if="!token"></div>
              <div class="rlv-btn-actividades-reg" @click="onSignUp()" v-if="token"></div>
            </div>
            
          </div>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>
<script>
export default {
  data() {
    return {
      token: '',     
    }
  },
  created() {
    if (process.client) {
      this.token = localStorage.getItem('token')
    }
  },
  watch: {
    '$store.state.user.token'(value) {
      if (value) {
        this.token = localStorage.getItem('token')
      }
    },
  },
  methods: {
    onOrientacion() {
      this.$router.push('/actividad-orientacion')
    },
    onSenderismo() {
      this.$router.push('/actividad-senderismo')
    },
    onAventuras() {
      this.$router.push('actividad-aventuras')
    },
    onMicologia() {
      this.$router.push('/actividad-micologia')
    },
    onSignUp() {
      this.$router.push('/sign-up')
    },
  },
}
</script>
