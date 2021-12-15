<template>
  <div class="rlv-rutas">
    <b-container>
      <div class="rlv-rutas-tittle">
        <h1 class="rlv-rutas-text">Rutas</h1>
        <b-img
          :src="require('../static/img/iconos/icono-rutas.png')"
          
        ></b-img>
        <h4 class="rlv-rutas-text">Este mes te ofrecemos</h4>
      </div>
      <b-row>
        <b-col cols="12" md="6" lg="4">
          <b-card
            :img-src="require('../static/img/rutas/01carneros.png')"
            img-alt="Image"
            img-top
            class="effect-image-1 zoom-effect-1 rlv-card rlv-pointer"
            @click="onClickCarneros()"
          >
            <b-card-text> <h3>Ruta de los carneros salvajes</h3> </b-card-text>
          </b-card>
        </b-col>
        <b-col cols="12" md="6" lg="4">
          <b-card
            :img-src="require('../static/img/rutas/02familia.png')"
            img-alt="Image"
            img-top
            class="effect-image-1 zoom-effect-1 rlv-card rlv-pointer"
             @click="onClickFamilia()"
          >
            <b-card-text>
              <h3>Ruta con todos los miembros de la familia</h3>
            </b-card-text>
          </b-card>
        </b-col>
        <b-col cols="12" md="6" lg="4">
          <b-card
            :img-src="require('../static/img/rutas/03nubes.png')"
            img-alt="Image"
            img-top
            class="effect-image-1 zoom-effect-1 rlv-card rlv-pointer"
            @click="onClickNubes()"
            
          >
            <b-card-text> <h3>Caminando entre las nubes</h3> </b-card-text>
          </b-card>
        </b-col>
        <b-col cols="12" md="6" lg="4">
          <b-card class="effect-image-1 zoom-effect-1 rlv-card rlv-pointer"
            :img-src="require('../static/img/rutas/04globos.png')"
            img-alt="Image"
            img-top
            @click="onClickGlobos()"
          
          >
            <b-card-text><h3>Vista a vuelo de pájaro</h3> </b-card-text>
          </b-card>
        </b-col>
        <b-col cols="12" md="6" lg="4">
          <b-card
            :img-src="require('../static/img/rutas/05cascadas.png')"
            img-alt="Image"
            img-top
            class="effect-image-1 zoom-effect-1 rlv-card rlv-pointer"
            @click="onClickCascadas()"
          >
            <b-card-text>
              <h3>Ruta entre cascadas y saltos de agua</h3>
            </b-card-text>
          </b-card>
        </b-col>
        <b-col cols="12" md="6" lg="4">
          <b-card-text class="solo-texto mt-4">
            <h3>Rutas y senderos programados para esta primavera.</h3>
            <h3>
              Apuntarse a las actividades implica la aceptación de las
              condiciones y normas de funcionamiento del club.
            </h3>
            <h3>
              Los organizadores de las excursiones o salidas podrán cambiar,
              modificar o anular, total o parcialmente, los itinerarios
              previstos si lo consideran necesario siempre por motivos de fuerza
              mayor.
            </h3>
          </b-card-text>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>
<script>
export default {
  methods: {
    onClickCarneros() {
      this.$router.push('./ruta-carneros')
    },
    onClickFamilia() {
      this.$router.push('./ruta-familia')
    },
    onClickNubes() {
      this.$router.push('./ruta-nubes')
    },
    onClickGlobos() {
      this.$router.push('./ruta-vuelo')
    },
    onClickCascadas() {
      this.$router.push('./ruta-cascadas')
    },
  },

}
</script>
