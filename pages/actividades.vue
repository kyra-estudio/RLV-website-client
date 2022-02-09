<template>
  <div class="rlv-actividades">
    <b-container class="rlv-actividades-container">
      <div class="rlv-rutas-tittle">
        <h1 class="rlv-rutas-text">Actividades</h1>
        <b-img
          :src="require('../static/img/iconos/icono-actividades.png')"
          fluid
        ></b-img>
      </div>
      <b-row>
        <b-col cols="12" md="12" lg="6">
          <div class="img-actividades d-flex justify-content-center">
            <b-img
              :src="require('../static/img/actividades/actividades.jpg')"
              fluid
            ></b-img>
          </div>
        </b-col>
        <b-col cols="12" md="12" lg="6">
          <div class="rlv-actividades-btn">
            <b-row class="mt-5" @click="onOrientacion()">
              <b-col cols="4" class="text-right">
                <b-img
                  :src="require('../static/img/iconos/i-orientacion.png')"
                  fluid
                ></b-img>
              </b-col>
              <b-col cols="8" align-self="center">
                <h4>Curso orientación</h4>
                <p>Muévete por la montaña sin miedo a perder el rumbo!</p>
              </b-col>
            </b-row>
            <b-row class="mt-4" @click="onSenderismo()">
              <b-col cols="4" class="text-right">
                <b-img
                  :src="require('../static/img/iconos/i-senderismo.png')"
                  fluid
                ></b-img>
              </b-col>
              <b-col cols="8" align-self="center">
                <h4>Senderismo</h4>
                <p>
                  Descubre las mejores rutas de senderismo en Madrid y
                  alrededores. ¡No te pierdas la próximas actividades!
                </p>
              </b-col>
            </b-row>
            <b-row class="mt-4" @click="onAventuras()">
              <b-col cols="4" class="text-right">
                <b-img
                  :src="require('../static/img/iconos/i-aventuras.png')"
                  fluid
                ></b-img>
              </b-col>
              <b-col cols="8" align-self="center">
                <h4>Aventuras</h4>
                <p>
                  El Parque Nacional de los Picos de Europa es, probablemente el
                  parque nacional más impresionante de España, o incluso de
                  Europa y, sin lugar a duda, un imán para los montañistas.
                </p>
              </b-col>
            </b-row>
            <b-row class="mt-4" @click="onMicologia()()">
              <b-col cols="4" class="text-right">
                <b-img
                  :src="require('../static/img/iconos/i-micologia.png')"
                  fluid
                ></b-img>
              </b-col>
              <b-col cols="8" align-self="center">
                <h4>Curso de micología</h4>
                <p>
                  Tanto si deseas adquirir una formación básica para poder
                  distinguir las setas más comunes en nuestros bosques como si
                  quieres afianzar tus conocimientos y despejar dudas, esta es
                  tu actividad.
                </p>
              </b-col>
            </b-row>
            
          </div>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>
<script>
export default {
  methods: {
    onOrientacion() {
      this.$router.push('/actividad-orientacion')
    },
    onSenderismo() {
      this.$router.push('/actividad-senderismo')
    },
    onAventuras() {
      this.$router.push('/actividad-aventuras')
    },
    onMicologia() {
      this.$router.push('/actividad-micologia')
    },
    
  }
}
</script>