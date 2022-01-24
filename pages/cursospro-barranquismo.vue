<template>
  <div class="rlv-cpro-barranquismo">
    <div class="rlv-subnav">
      <p hidden>{{title}}</p>
      <b-nav>
        <b-nav-item @click="onEscalada()" class="rlv-subnav-item"
          >Escalada</b-nav-item
        >
        <b-nav-item @click="onRafting()" class="rlv-subnav-item"
          >Rafting</b-nav-item
        >
        <b-nav-item @click="onParapente()" class="rlv-subnav-item" 
          >Parapente
        </b-nav-item>
        <b-nav-item @click="onBarranquismo()" class="rlv-subnav-item" active
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
        :img-src="require('../static/img/cursospro/banner-barranquismo.png')"
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
                Si le interesa el entorno del deporte y quiere conocer las técnicas necesarias para desempeñar la función de monitor y guía en descenso de barrancos este es su momento, con el Curso de monitor y guía en descenso de barrancos podrá adquirir los conocimientos necesarios para desempeñar esta labor de la mejor manera posible. 
              </p>
            </div>
          </b-col>
        </b-row>
      </div>
    </b-container>
    <b-row>
      <b-col lg="12">
        <b-img
          :src="require('../static/img/cursospro/barranquismo1.png')"
          fluid
        ></b-img>
      </b-col>
    </b-row>
    <b-row class="mt-3">
      <b-col lg="12">
        <b-img
          :src="require('../static/img/cursospro/barranquismo2.png')"
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
          if (data.activity[i].title === config.proBarranquismoName) {
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
