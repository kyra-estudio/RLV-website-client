<template>
  <div class="rlv-orientacion">
    <div class="rlv-subnav">
      <b-nav>
        <b-nav-item @click="onOrientacion()" class="rlv-subnav-item" 
          >Curso Orientación</b-nav-item
        >
        <b-nav-item @click="onSenderismo()" class="rlv-subnav-item"
          >Senderismo</b-nav-item
        >
        <b-nav-item @click="onAventuras()" class="rlv-subnav-item" active
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
                  :src="require('../static/img/iconos/i-aventuras.png')"
                  fluid
                ></b-img>
              </div>
            </b-col>
            <b-col cols="4">
              <h1 class="rlv-title-cursos">{{title}}</h1>
              <p class="rlv-text-cursos">
                Apuntarse a las actividades implica la aceptación de las
                condiciones y normas de funcionamiento del club.
              </p>
              <p class="rlv-text-cursos">
                El Parque Nacional de los Picos de Europa es, probablemente el parque nacional más impresionante de España, o incluso de Europa y, sin lugar a duda, un imán para los montañistas.
              </p>              
            </b-col>
            <b-col cols="2"></b-col>
          </b-row>
        </b-col>
        <b-col cols="12" md="12" lg="6">
          <div class="img-actividades d-flex justify-content-center">
            
            <b-img
              :src="require('../static/img/actividades/aventuras.png')"
              fluid
            ></b-img>
            <div class="rlv-btn-actividades-pst">
              <div class="rlv-btn-actividades" @click="onSignUp()" v-if="!token"></div>
              <div class="rlv-btn-actividades-reg" @click="onForm()" v-if="token"></div>
            </div>
            
          </div>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>
<script>
import config from '~/config'
export default {
  data() {
    return {
      token: '',
      currdeg: 0,
      title: '',
    }
  },
  created() {
    if (process.client) {
      this.token = localStorage.getItem('token')
    }
  },
  beforeMount() {
    this.loadActivity()
  },
  computed: {
    style() {
      return { transform: 'rotateY(' + this.currdeg + 'deg)' }
    },
  },
  watch: {
    '$store.state.user.token'(value) {
      if (value) {
        this.token = localStorage.getItem('token')
      }
    },
  },

  methods: {
    async loadActivity() {
      try {
        const res = await fetch('http://localhost:4500/api/activity/getAll', {
          method: 'GET',
        })
        const data = await res.json()
        for (let i = 0; i < data.activity.length; i++) {
          if (data.activity[i].title === config.actividadAventurasName) {
            this.title = data.activity[i].title
            localStorage.setItem('activityId', data.activity[i]._id)
            localStorage.setItem('activityName', data.activity[i].title)
          }
        }
      } catch (err) {
        alert(err.message)
      }
    },
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
    onForm() {
      this.$router.push('/formulario-actividades')
    },
  },
}
</script>
