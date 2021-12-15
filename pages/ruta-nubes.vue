<template>
  <div class="rlv-nubes">
    <div class="rlv-subnav">
      <b-nav>
        <b-nav-item @click="onCarneros()" class="rlv-subnav-item"
          >Ruta de los carneros salvajes</b-nav-item
        >
        <b-nav-item @click="onFamilia()" class="rlv-subnav-item"
          >Ruta con todos los miembros de la familia</b-nav-item
        >
        <b-nav-item active @click="onNubes()" class="rlv-subnav-item"
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
    <b-container>
      <div class="container_3d">
        <div class="carousel_3d" v-bind:style="style">
          <div class="item_3d a">A</div>
          <div class="item_3d b">B</div>
          <div class="item_3d c">C</div>
          <div class="item_3d d">D</div>
          <div class="item_3d e">E</div>
          <div class="item_3d f">F</div>
        </div>
      </div>
      <div class="next" @click="rotate('n')">Next</div>
      <div class="prev" @click="rotate('p')">Prev</div>
    </b-container>
  </div>
</template>
<script>
export default {
  data() {
    return {
      currdeg: 0,
    }
  },
  computed: {
    style () {
        return { transform: 'rotateY(' + this.currdeg + 'deg)'}
     }
  },
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
    rotate(action) {
      if (action == 'n') {
        this.currdeg = this.currdeg - 60
      }
      if (action == 'p') {
        this.currdeg = this.currdeg + 60
      }
    },
  },
}
</script>
