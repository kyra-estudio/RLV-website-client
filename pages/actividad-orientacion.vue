<template>
  <div class="rlv-orientacion">
    <div class="rlv-subnav">
      <b-nav>
        <b-nav-item @click="onOrientacion()" class="rlv-subnav-item" active
          >Curso Orientación</b-nav-item
        >
        <b-nav-item @click="onSenderismo()" class="rlv-subnav-item"
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
                  :src="require('../static/img/iconos/i-orientacion.png')"
                  fluid
                ></b-img>
              </div>
            </b-col>
            <b-col cols="4">
              <h1 class="rlv-title-cursos">Curso Orientación</h1>
              <p class="rlv-text-cursos">
                Apuntarse a las actividades implica la aceptación de las
                condiciones y normas de funcionamiento del club.
              </p>
              <p class="rlv-text-cursos">
                Muévete por la montaña sin miedo a perder el rumbo!
              </p>
              <p class="rlv-text-cursos">
                En la Escuela Madrileña Relieve tenemos el curso de orientación
                que se adapta a tu nivel y a tus necesidades, con grupos
                reducidos, una enseñanza personalizada y las metodologías más
                innovadoras del sector del outdoor.
              </p>
            </b-col>
            <b-col cols="2"></b-col>
          </b-row>
        </b-col>
        <b-col cols="12" md="12" lg="6">
          <div class="img-actividades d-flex justify-content-center">
            <b-img
              :src="require('../static/img/actividades/orientacion.png')"
              fluid
            ></b-img>
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
      this.$router.push('actividad-aventuras')
    },
    onMicologia() {
      this.$router.push('/actividad-micologia')
    },
  },
}
</script>
