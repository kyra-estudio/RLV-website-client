<template>
  <div class="rlv-ruta-familias">
    <div class="rlv-subnav">
      <b-nav>
        <b-nav-item @click="onCarneros()" class="rlv-subnav-item"
          >Ruta de los carneros salvajes</b-nav-item
        >
        <b-nav-item @click="onFamilia()" class="rlv-subnav-item" active
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
              :src="require('../static/img/rutas/ruta-familia-xl.png')"
              fluid
            ></b-img>
          </div>
        </b-col>
        <b-col cols="12" md="12" lg="4">
          <div class="text-rutas-detalle">
            <h1>{{ title }}</h1>
            <b-img
              :src="require('../static/img/iconos/incluye.png')"
              fluid
            ></b-img>
            <div class="button" v-if="!token">
              <p class="clic">Reserva tu plan desde 200€</p>
              <div class="rlv-btn-rutas">
                <p class="rlv-sure" @click="goSignUp()">Regístrate!</p>
              </div>
            </div>
            <div class="button" v-else>
              <p class="clic">Reserva tu plan desde 200€</p>
              <div class="rlv-btn-rutas">
                <p class="rlv-sure" @click="onForm()">+ info!</p>
              </div>
            </div>
            <h2>
              Parque natural de Somiedo, Asturias, declarado espacio natural
              Reserva de la Bioesfera.
            </h2>
            <p>
              El Parque Natural de Somiedo es uno de los últimos reductos donde
              la naturaleza es pura. Sus paisajes, su fauna y flora, su
              gastronomía, y sus gentes hacen de este rincón un lugar
              privilegiado.
            </p>
            <p>
              De su accidentado paisaje que va desde los 400 metros a los casi
              2.200, destacan sus impresionantes lagos, los de Saliencia y del
              Valle, sus brañas, como la Pornacal, Mumián o Sousas, en las que
              podemos encontrar los teitos, construcciones que utilizaban los
              vaqueiros de alzada realizadas con techumbre de escoba.
            </p>
          </div>
        </b-col>
      </b-row>
      <b-row class="rlv-carrusel_3d">
        <div class="container_3d">
          <div class="carousel_3d" v-bind:style="style">
            <div class="item_3d a">
              <b-img
                :src="require('../static/img/rutas/somiedo01.jpg')"
                fluid
              />
            </div>
            <div class="item_3d b">
              <b-img
                :src="require('../static/img/rutas/somiedo02.jpg')"
                fluid
              />
            </div>
            <div class="item_3d c">
              <b-img
                :src="require('../static/img/rutas/somiedo03.jpg')"
                fluid
              />
            </div>
            <div class="item_3d d">
              <b-img
                :src="require('../static/img/rutas/somiedo04.jpg')"
                fluid
              />
            </div>
            <div class="item_3d e">
              <b-img
                :src="require('../static/img/rutas/somiedo05.jpg')"
                fluid
              />
            </div>
            <div class="item_3d f">
              <b-img
                :src="require('../static/img/rutas/somiedo06.jpg')"
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
            title="Conjunto lacuestre de los lagos de Somiedo. "
            :img-src="require('../static/img/rutas/conjunto_lacuestre.png')"
            img-top
            tag="article"
            style=""
            class="rlv-card-rutas-detalles mb-2"
          >
            <b-card-text>
              Hay muchas cosas que hacer en Somiedo, pero una que no te puedes
              perder y a la que hay que dedicarle un día, es a conocer los lagos
              de Somiedo. El conjunto lacuestre de los lagos de Somiedo o Lagos
              de Saliencia, como también se les conoce, está formado por los
              lagos Cerveriz, la Cueva, Calabazosa o Negro, la Mina o Almagrera,
              y el famoso lago del Valle, el mas grande de Asturias.
            </b-card-text>
          </b-card>
        </b-col>
        <b-col cols="12" md="6" lg="4">
          <b-card
            title="Valle del Glaciar."
            :img-src="
              require('../static/img/rutas/valle_del_glaciar-Somiedo.png')
            "
            img-top
            tag="article"
            style=""
            class="rlv-card-rutas-detalles mb-2"
          >
            <b-card-text>
              Si lo que prefieres es conocer los lagos de Somiedo en dos dias y
              sin Prisas, puedes planificar tu visita recorriendo todos los
              lagos menos uno en un dia, y dejando el lago del Valle para otro
              día, si lo planificas de esta manera, lo mejor es que accedas al
              lago del Valle desde la poblacioón de Valle del Lago, y desde aquí
              asciendas hacia el lago por el valle llanado también Valle del
              Lago (parece un galimatías).
            </b-card-text>
          </b-card>
        </b-col>
        <b-col cols="12" md="6" lg="4">
          <b-card
            title="Desfiladero río Somiedo."
            :img-src="require('../static/img/rutas/rio_somiedo.png')"
            img-top
            tag="article"
            style=""
            class="rlv-card-rutas-detalles mb-2"
          >
            <b-card-text>
              El río Somiedo es quien da nombre al Parque Natural, y no es de
              extrañar porque nace en su extremo sur, cerca del Puerto de
              Somiedo (divisoria entre La Babia leonesa y el Somiedo asturiano),
              muere en el límite norte del parque al desembocar en el río
              Pigüeña en Entrambasaguas.
            </b-card-text>
          </b-card>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>
<script>
import config from '~/config'
export default {
  data() {
    return {
      token: '',
      currdeg: 0,
      title: '',
    }
  },
  created() {
    if (process.client) {
      this.token = localStorage.getItem('token')
    }
  },
  beforeMount() {
    this.loadActivity()
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
    async loadActivity() {
      try {
        const res = await fetch('http://localhost:4500/api/activity/getAll', {
          method: 'GET',
        })
        const data = await res.json()
        for (let i = 0; i < data.activity.length; i++) {
          if (data.activity[i].title === config.rutaFamiliaName) {
            this.title = data.activity[i].title
            localStorage.setItem('activityId', data.activity[i]._id)
            localStorage.setItem('activityName', data.activity[i].title)
          }
        }
      } catch (err) {
        alert(err.message)
      }
    },
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
    onForm() {
      this.$router.push('/formulario-actividades')
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
