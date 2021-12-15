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
    <b-container>
      <b-row class="rlv-ruta-detalle">
        <b-col cols="12" md="12" lg="8">
          <div class="rlv-imagen-ruta-detalle">
            <b-img
              :src="require('../static/img/rutas/ruta-carneros-xl.png')"
              fluid
            ></b-img>
          </div>
        </b-col>
        <b-col cols="12" md="12" lg="4">
          <div class="text-rutas-detalle">
            <h1>Ruta de los carneros salvajes</h1>
            <b-img
              :src="require('../static/img/iconos/incluye.png')"
              fluid
            ></b-img>
            <div class="button">
              <p class="clic">Reserva tu plan desde 200€</p>
              <div class="hover">
                <p class="sure" @click="goSignUp()" v-if="!token">
                  Regístrate!
                </p>
                <p class="sure" @click="goSignUp()" v-if="token">+ info!</p>
              </div>
            </div>
            <h2>
              Caminando por el impresionante paisaje de alta montaña de la Val
              d’Aran.
            </h2>
            <p>
              El Valle de Arán es un lugar único y de singular belleza, y hace
              que miles de turistas de todo el mundo visiten esta zona. Te
              mostramos algunos de los mejores lugares que ver en el Valle de
              Aran: Lugares como el Circo de Colomers, o Montgarri. Pueblos como
              Bossòst o Bausén de arquitectura típica aranesa, no dejan
              indiferente al visitante.El Valle de Arán es un lugar único y de
              singular belleza, y hace que miles de turistas de todo el mundo
              visiten esta zona. Te mostramos algunos de los mejores lugares que
              ver en el Valle de Aran: Lugares como el Circo de Colomers, o
              Montgarri. Pueblos como Bossòst o Bausén de arquitectura típica
              aranesa, no dejan indiferente al visitante.
            </p>
          </div>
        </b-col>
      </b-row>
      <b-row class="rlv-carrusel_3d">
        <div class="container_3d">
          <div class="carousel_3d" v-bind:style="style">
            <div class="item_3d a">
              <b-img
                :src="require('../static/img/rutas/v-aran-01.png')"
                fluid
              />
            </div>
            <div class="item_3d b">
              <b-img
                :src="require('../static/img/rutas/v-aran-02.png')"
                fluid
              />
            </div>
            <div class="item_3d c">
              <b-img
                :src="require('../static/img/rutas/v-aran-03.png')"
                fluid
              />
            </div>
            <div class="item_3d d">
              <b-img
                :src="require('../static/img/rutas/v-aran-04.png')"
                fluid
              />
            </div>
            <div class="item_3d e">
              <b-img
                :src="require('../static/img/rutas/v-aran-05.png')"
                fluid
              />
            </div>
            <div class="item_3d f">
              <b-img
                :src="require('../static/img/rutas/v-aran-06.png')"
                fluid
              />
            </div>
          </div>
        </div>
        <div class="next" @click="rotate('n')">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="50"
            height="50"
            fill="currentColor"
            class="bi bi-arrow-right-circle-fill next-arrow"
            viewBox="0 0 16 16"
          >
            <path
              d="M8 0a8 8 0 1 1 0 16A8 8 0 0 1 8 0zM4.5 7.5a.5.5 0 0 0 0 1h5.793l-2.147 2.146a.5.5 0 0 0 .708.708l3-3a.5.5 0 0 0 0-.708l-3-3a.5.5 0 1 0-.708.708L10.293 7.5H4.5z"
            />
          </svg>
        </div>
        <div class="prev" @click="rotate('p')">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="50"
            height="50"
            fill="currentColor"
            class="bi bi-arrow-left-circle-fill prev-arrow"
            viewBox="0 0 16 16"
          >
            <path
              d="M8 0a8 8 0 1 0 0 16A8 8 0 0 0 8 0zm3.5 7.5a.5.5 0 0 1 0 1H5.707l2.147 2.146a.5.5 0 0 1-.708.708l-3-3a.5.5 0 0 1 0-.708l3-3a.5.5 0 1 1 .708.708L5.707 7.5H11.5z"
            />
          </svg>
        </div>
      </b-row>

      <b-row class="mt-5">
        <b-col cols="12" md="6" lg="4">
          <b-card
            title="Un lugar único en el mundo. "
            :img-src="require('../static/img/rutas/aran01.png')"
            img-top
            tag="article"
            style=""
            class="rlv-card-rutas-detalles mb-2"
          >
            <b-card-text>
              El Valle de Arán es un lugar único y de singular belleza, y hace
              que miles de turistas de todo el mundo visiten esta zona. Te
              mostramos algunos de los mejores lugares que ver en el Valle de
              Aran: Lugares como el Circo de Colomers, o Montgarri. Pueblos como
              Bossòst o Bausén de arquitectura típica aranesa, no dejan
              indiferente al visitante.
            </b-card-text>
          </b-card>
        </b-col>
        <b-col cols="12" md="6" lg="4">
          <b-card
            title="Vielha y Baqueira Beret."
            :img-src="require('../static/img/rutas/aran02.png')"
            img-top
            tag="article"
            style=""
            class="rlv-card-rutas-detalles mb-2"
          >
            <b-card-text>
              Vielha, con sus 2.046 habitantes es la capital de Val D’Aran, sede
              del Conselh Generau d’Aran y el centro de un gran condado,
              conocido como Vielha e Mijaran, que abarca los pueblos de Escunhau
              (iglesia románica notable), Betren, Casarilh, Gausac, Casau,
              Vilac, Betlan, Aubert, Mont, Montcorbau, Arros y Vila y el
              santuario de Santa María de Mijaran.
            </b-card-text>
          </b-card>
        </b-col>
        <b-col cols="12" md="6" lg="4">
          <b-card
            title="Valle de Arán Pueblos."
            :img-src="require('../static/img/rutas/aran03.png')"
            img-top
            tag="article"
            style=""
            class="rlv-card-rutas-detalles mb-2"
          >
            <b-card-text>
              El Valle de Arán está situado en la vertiente atlántica de los
              Pirineos, a diferencia de otros valles pirenaicos catalanes que se
              encuentran en el lado mediterráneo de la cordillera y miran hacia
              el sur. Su orientación lo convierte en un valle con una diferencia
              que se revela.
            </b-card-text>
          </b-card>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>
<script>
export default {
  data() {
    return {
      token: '',
      currdeg: 0,
    }
  },
  created() {
    if (process.client) {
      this.token = localStorage.getItem('token')
    }
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
