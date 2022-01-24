<template>
  <div class="rlv-cpro-parapente">
    <div class="rlv-subnav">
      <b-nav>
        <b-nav-item @click="onEscalada()" class="rlv-subnav-item"
          >Escalada</b-nav-item
        >
        <b-nav-item @click="onRafting()" class="rlv-subnav-item"
          >Rafting</b-nav-item
        >
        <b-nav-item @click="onParapente()" class="rlv-subnav-item" active
          >Parapente
        </b-nav-item>
        <b-nav-item @click="onBarranquismo()" class="rlv-subnav-item"
          >Barranquismo
        </b-nav-item>
      </b-nav>
    </div>
    <b-carousel
      id="carousel-no-animation"
      no-animation
      img-width="1024"
      img-height="400"
    >
      <b-carousel-slide
        :img-src="require('../static/img/cursospro/banner-parapente.png')"
      ></b-carousel-slide>
    </b-carousel>
    <b-container>
      <div>
        <b-row>
          <b-col lg="5">
            <div class="rlv-escalada-titulo">
              <b-img
                :src="require('../static/img/cursospro/titulo.png')"
                fluid
              ></b-img>
            </div>
          </b-col>
          <b-col lg="2">
            <div class="rlv-btn-cursospro-pst">
              <div class="rlv-btn-cursospro-reg" @click="onForm()"></div>
            </div>
          </b-col>
          <b-col lg="5">
            <div>
              <p class="rlv-escalada-text">
                El parapente como actividad profesional comienza con los Cursos
                de Técnico Deportivo Nivel I. Para hacer biplazas en parapente,
                enseñar a volar o trabajar en una escuela de parapente necesitas
                esta formación y el titulo que proporciona, con validez nacional
                y europea (es una formación profesional deportiva de grado
                medio).
              </p>
            </div>
          </b-col>
        </b-row>
      </div>
    </b-container>
    <b-row>
      <b-col lg="12">
        <b-img
          :src="require('../static/img/cursospro/parapente1.png')"
          fluid
        ></b-img>
      </b-col>
    </b-row>
    <b-row class="mt-3">
      <b-col lg="12">
        <b-img
          :src="require('../static/img/cursospro/parapente2.png')"
          fluid
        ></b-img>
      </b-col>
    </b-row>
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
          if (data.activity[i].title === config.proParapenteName) {
            this.title = data.activity[i].title
            localStorage.setItem('activityId', data.activity[i]._id)
            localStorage.setItem('activityName', data.activity[i].title)
          }
        }
      } catch (err) {
        alert(err.message)
      }
    },
    onEscalada() {
      this.$router.push('/cursospro-escalada')
    },
    onRafting() {
      this.$router.push('/cursospro-rafting')
    },
    onParapente() {
      this.$router.push('/cursospro-parapente')
    },
    onBarranquismo() {
      this.$router.push('/cursospro-barranquismo')
    },
    onForm() {
      this.$router.push('/formulario-actividades')
    },
  },
}
</script>
