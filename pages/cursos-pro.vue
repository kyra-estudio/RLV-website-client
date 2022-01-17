<template>
  <div class="rlv-cursosPro">
    <b-carousel
      id="carousel-no-animation"
      no-animation
      img-width="1024"
      img-height="480"
    >
      <b-carousel-slide
        :img-src="require('../static/img/cursospro/banner-portada.png')"
      ></b-carousel-slide>
    </b-carousel>
    <b-container>
      <div>
        <b-row>
          <b-col cols="12" md="6" lg="8">
            <div class="rlv-cursospro-titulo">
              <b-img
                :src="require('../static/img/cursospro/titulo.png')"
                fluid
              ></b-img>
            </div>
            <div>
              <p class="rlv-cursospro-text">
                El curso de preparación para el examen de técnico en Guía Rural
                tiene por finalidad formar profesionales que dispongan de los
                conociminetos exigidos para la práctica profesional. este curso
                de Ciclo Formativo de Grado Medio se realiza en modalidad a
                distancia. Obtén el Diploma de la Asociación Española de
                Enseñanza Técnico Profesional de Guía Turístico Rural, que te
                interesa personal y profesionalmente...
              </p>
            </div>
          </b-col>
          <b-col cols="12" md="6" lg="4" class="mt-3">
            <div class="rlv-cursospro-iconos">
              <div  class="rlv-cursospro-i-escalada" @click="onEscalada()">
                <b-img
                :src="require('../static/img/iconos/i-escalada.png')"
              ></b-img>
              </div>
              <div class="rlv-cursospro-i-rafting" @click="onRafting()">
                <b-img
                :src="require('../static/img/iconos/i-rafting.png')"
              ></b-img>
              </div>
              <div class="rlv-cursospro-separador">
                <b-img
                :src="require('../static/img/cursospro/separador.png')"
              ></b-img>
              </div>
              <div class="rlv-cursospro-i-parapente" @click="onParapente()">
                <b-img
                :src="require('../static/img/iconos/i-parapente.png')"
              ></b-img>
              </div>
              <div class="rlv-cursospro-i-barranquismo" @click="onBarranquismo()">
                <b-img
                :src="require('../static/img/iconos/i-barranquismo.png')"
              ></b-img>
              </div>
            </div>
               </b-col>
        </b-row>
      </div>
    </b-container>
  </div>
</template>
<script>
export default {
  data() {
    return {
      token: '',
      avatar: undefined,
      name: '',
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
   methods: {
    onEscalada() {
      this.$router.push('/cursospro-escalada')
    },
    onRafting() {
      this.$router.push('/cursospro-rafting')
    },
    onParapente() {
      this.$router.push('cursospro-parapente')
    },
    onBarranquismo() {
      this.$router.push('/cursospro-barranquismo')
    },
    
  },

  
}
</script>
