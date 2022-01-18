<template>
  <div class="rlv-cpro-barranquismo">
    <div class="rlv-subnav">
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
              <div class="rlv-btn-cursospro-reg" @click="onSignUp()"></div>
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
  },
}
</script>
