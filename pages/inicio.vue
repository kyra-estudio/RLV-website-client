<template>
  <div class="rls-inicio">
    <RLVCarrusel />
    <b-container>
      <b-row class="mt-2">
        <b-col cols="lg-9">
          <p class="rlv-claim-tex">
            Nunca es tarde para conocer la belleza de la naturaleza
          </p>
          <p class="rlv-subclaim-text">
            Todos podemos ver espectaculares fotografías, pero ¿no preferiríais
            vivirlas? El tiempo y el esfuerzo que requiere ascender una montaña
            no están al alcance de todos. Cuando pisas una cumbre puedes estar
            bastante seguro de que eres de una minoría y de que el paisaje que
            contemplas lo han visto pocos ojos.
          </p>
        </b-col>
        <b-col cols="lg-3">
          <div class="rlv-btn-inicio">
            <b-button class="btn-rutas" size="lg" img @click="goRutas()">
              <img :src="require('../static/img/iconos/rutas.png')" />
            </b-button>
          </div>
          <div class="">
            <b-button class="btn-rutas" size="lg" @click="goActividades()">
              <img :src="require('../static/img/iconos/actividades.png')" />
            </b-button>
          </div>
          <div>
            <b-button class="btn-rutas" size="lg" @click="goCursosPro()">
              <img :src="require('../static/img/iconos/cursosPro.png')" />
            </b-button>
          </div>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>
<script>
export default {
  methods: {
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
