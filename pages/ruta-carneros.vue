<template>
  <div class="rlv-ruta-carneros">
    <div class="rlv-subnav">
      <b-nav>
        <b-nav-item @click="onCarneros()" class="rlv-subnav-item" active
          >Ruta de los carneros salvajes</b-nav-item
        >
        <b-nav-item @click="onFamilia()" class="rlv-subnav-item"
          >Ruta con todos los miembros de la familia</b-nav-item
        >
        <b-nav-item @click="onNubes()" class="rlv-subnav-item"
          >Caminando entre nubes
        </b-nav-item>
        <b-nav-item @click="onVuelo()" class="rlv-subnav-item"
          >Vista a vuelo de pájaro
        </b-nav-item>
        <b-nav-item @click="onCascadas()" class="rlv-subnav-item"
          >Ruta entre cascadas y saltos de agua
        </b-nav-item>
      </b-nav>
    </div>
    <b-container fluid>
      <b-row class="rlv-ruta-detalle">
        <b-col cols="8">
          <div class="rlv-imagen-ruta-detalle">
            <b-img
              :src="require('../static/img/rutas/ruta-carneros-xl.png')"
              fluid
            ></b-img>
          </div>
        </b-col>
        <b-col cols="4">
          <div class="text-rutas-detalle">
            <h1>Ruta de los carneros salvajes</h1>
            <b-img
              :src="require('../static/img/iconos/incluye.png')"
              fluid
            ></b-img>
            <div class="button">
              <p class="clic">Reserva tu plan desde 200€</p>
              <div class="hover">
                <p class="sure" @click="goSignUp()">Regístrate!</p>                
              </div>
              <!-- <div class="hover">
                <p class="sure">+ info!</p>                
              </div> -->
            </div>
          </div>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>
<script>
export default {
  methods: {
    onCarneros() {
      this.$router.push('/ruta-carneros')
    },
    onFamilia() {
      this.$router.push('/ruta-familia')
    },
    onNubes() {
      this.$router.push('/ruta-nubes')
    },
    onVuelo() {
      this.$router.push('/ruta-vuelo')
    },
    onCascadas() {
      this.$router.push('/ruta-cascadas')
    },
     goSignUp() {
      this.$router.push('/sign-up')
    },
  },
}
</script>
