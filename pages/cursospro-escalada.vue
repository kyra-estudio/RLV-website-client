<template>
  <div class="rlv-cpro-escalada">
    <div class="rlv-subnav">
      <b-nav>
        <b-nav-item @click="onEscalada()" class="rlv-subnav-item" active
          >Escalada</b-nav-item
        >
        <b-nav-item @click="onRafting()" class="rlv-subnav-item"
          >Rafting</b-nav-item
        >
        <b-nav-item @click="onParapente()" class="rlv-subnav-item"
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
        :img-src="require('../static/img/cursospro/banner-escalada.png')"
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
                El título de MONITOR VOLUNTARIO EN ESCALADA acredita que la
                persona titular posee los conocimientos necesarios para
                organizar las actividades/salidas de escalada de los clubes, de
                forma segura y adecuadas al nivel del grupo, en el ámbito de la
                escalada deportiva en vías bien equipadas de un solo largo en
                rocódromo o roca.
              </p>
            </div>
          </b-col>
        </b-row>
      </div>
    </b-container>
    <b-row>
      <b-col lg="6">
        <b-img
          :src="require('../static/img/cursospro/escalada1.jpg')"
          fluid
        ></b-img>
      </b-col>
      <b-col lg="6" class="rlv-escalda-imgright">
        <div class="rlv-escalada-escalada2">
          <b-img
            :src="require('../static/img/cursospro/escalada2.png')"
            fluid
          ></b-img>
        </div>
        <div class="rlv-escalada-escalada3">
          <b-img
            :src="require('../static/img/cursospro/escalada3.png')"
            fluid
          ></b-img>
        </div>
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
