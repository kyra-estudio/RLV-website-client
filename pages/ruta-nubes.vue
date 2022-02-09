<template>
  <div class="rlv-ruta-nubes">
    <div class="rlv-subnav d-none d-lg-block">
      <b-nav>
        <b-nav-item @click="onCarneros()" class="rlv-subnav-item"
          >Ruta de los carneros salvajes</b-nav-item
        >
        <b-nav-item @click="onFamilia()" class="rlv-subnav-item"
          >Ruta con todos los miembros de la familia</b-nav-item
        >
        <b-nav-item @click="onNubes()" class="rlv-subnav-item" active
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
              :src="require('../static/img/rutas/ruta-nubes-xl.png')"
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
              Como ya supondrás Babia existe y lo que allí se descubres
              justifica a tanto ensimismamiento.
            </h2>
            <p>
              Bajo la vigilancia de la inmensa mole rocosa de Peña Ubiña (2.417
              metros) se desarrolla el abrupto paisaje montañoso del Valle de
              San Emiliano.
            </p>
            <p>
              A caballo entre los valles leoneses de Babia y Luna, en el mismo
              confín de Asturias, este valle presenta, junto a las clásicas
              huellas de la erosión glaciar, las no menos significativas
              muestras del relieve kárstico. Entre la vegetación presente
              destacan las masas de haya, roble y el relicto sabinar -el más
              occidental de la Península Ibérica- de Mirantes de Luna. Destaca
              la intensa actividad tradicional desarrollada por la trashumancia
              de las ovejas merinas en esta zona, y a la pervivencia de
              diferentes razas autóctonas como los caballos Hispano-bretones y
              los mastines leoneses.
            </p>
          </div>
        </b-col>
      </b-row>
      <b-row class="rlv-carrusel_3d">
        <div class="container_3d">
          <div class="carousel_3d" v-bind:style="style">
            <div class="item_3d a">
              <b-img :src="require('../static/img/rutas/babia01.jpg')" fluid />
            </div>
            <div class="item_3d b">
              <b-img :src="require('../static/img/rutas/babia02.jpg')" fluid />
            </div>
            <div class="item_3d c">
              <b-img :src="require('../static/img/rutas/babia03.jpg')" fluid />
            </div>
            <div class="item_3d d">
              <b-img :src="require('../static/img/rutas/babia04.jpg')" fluid />
            </div>
            <div class="item_3d e">
              <b-img :src="require('../static/img/rutas/babia05.jpg')" fluid />
            </div>
            <div class="item_3d f">
              <b-img :src="require('../static/img/rutas/babia06.jpg')" fluid />
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
            title="Peña Urbiña. "
            :img-src="require('../static/img/rutas/conjunto_lacuestre.png')"
            img-top
            tag="article"
            style=""
            class="rlv-card-rutas-detalles mb-2"
          >
            <b-card-text>
              La ruta transcurre por un paisaje de alta montaña, dominado por
              pastizales de una gran belleza. Las vistas panorámicas a toda la
              Reserva de la Biosfera de Babia, así como a los territorios
              aledaños son impresionantes. Desde el collado, y para los más
              aventureros se puede acceder a la cima de Peh, siempre teniendo
              las precauciones que requiere el acceso a pico de estas
              características.Por historia, porque Ubiña es tierra de
              trashumancia, de ovejas, pastores y mastines, de gentes que desde
              Extremadura subían cada verano a aprovechar los verdes campos de
              Babia, utilizados también por los reyes de León para su descanso
              bélico y político. Porque en Ubiña también se libraron importantes
              acontecimientos de la guerra civil española. Trincheras y restos
              de proyectiles pueblan estas crestas.
            </b-card-text>
          </b-card>
        </b-col>
        <b-col cols="12" md="6" lg="4">
          <b-card
            title="Riogalo de Babia."
            :img-src="require('../static/img/rutas/riogalo.png')"
            img-top
            tag="article"
            style=""
            class="rlv-card-rutas-detalles mb-2"
          >
            <b-card-text>
              Riolago se encuentra desde el s. XV entre las propiedades de la
              poderosa familia de los Quiñones. Esta rama familiar funda en 1512
              el mayorazgo de Riolago. Como muestra de su importancia, los
              Quiñones habilitan una casa fuerte y palacio (s.XVI), que por
              mucho tiempo fue conocido el Palacio de la Torre Redonda. Tras
              muchos avatares y pasar por muchas manos, sufrió un incendio en
              1915 que determinó su ruina, hasta que, adquirido por Don Fernando
              Geijo, fue reconstruido según su estilo original, siendo el
              palacio que hoy se conserva propiedad de la Junta de Castilla y
              León. El Palacio consta de residencia con torre, ahora cuadrada,
              una pequeña capilla y las caballerizas, todo amurallado, a modo de
              fortaleza.
            </b-card-text>
          </b-card>
        </b-col>
        <b-col cols="12" md="6" lg="4">
          <b-card
            title="Las fuentes del Sil."
            :img-src="require('../static/img/rutas/fuentes-sol.png')"
            img-top
            tag="article"
            style=""
            class="rlv-card-rutas-detalles mb-2"
          >
            <b-card-text>
              La ruta de las Fuentes del Sil es un recorrido de 11 km que parte
              de la localidad de La Cueta, y transcurre a lo largo del primer
              tramo del río Sil, hasta las fuentes que dan lugar a su
              nacimiento, al pie de Peña Orniz (2.191m). Prácticamente todo el
              recorrido transcurre por veredas entre los pastizales de puerto,
              donde es posible observar durante el verano grandes rebaños de
              ovejas merinas aprovechando la calidad de este pastizal. Desde el
              final de esta ruta es posible acceder, con las precauciones
              necesarias, a Peña Orniz desde donde es posible observar unas
              interesantes vistas panorámicas de Babia.
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
      title: ""
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
        const url = config.HOSTNAME + 'api/activity/getAll'
        const res = await fetch(url, {
          method: 'GET',
        })
        const data = await res.json()
        for (let i = 0; i < data.activity.length; i++) {
          if (data.activity[i].title === config.rutaNubesName) {
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
