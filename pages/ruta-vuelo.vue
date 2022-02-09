<template>
  <div class="rlv-ruta-vuelo">
    <div class="rlv-subnav d-none d-lg-block">
      <b-nav>
        <b-nav-item @click="onCarneros()" class="rlv-subnav-item"
          >Ruta de los carneros salvajes</b-nav-item
        >
        <b-nav-item @click="onFamilia()" class="rlv-subnav-item"
          >Ruta con todos los miembros de la familia</b-nav-item
        >
        <b-nav-item @click="onNubes()" class="rlv-subnav-item"
          >Caminando entre nubes
        </b-nav-item>
        <b-nav-item @click="onVuelo()" class="rlv-subnav-item" active
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
              :src="require('../static/img/rutas/ruta-vuelo-xl.png')"
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
            <h2>Sierra y cañones de Guara, Alquézar.</h2>
            <p>
              No se entiende el Parque Natural de la Sierra y los Cañones de
              Guara sin los cauces de aguas cristalinas que cruzan todo el
              paisaje de norte a sur. Ríos furiosos que excavan la roca, presas
              de color azul turquesa, pozas de ensueño y cascadas inesperadas.
            </p>
            <p>
              La visión de un paisaje en principio de aspecto inhóspito se
              transforma en un pequeño paraíso terrenal en estas tierras.
              Gracias a la abundancia del agua nos podemos pegar un estupendo
              chapuzón en alguna de las variadas pozas y piscinas naturales que
              completan el parque. Un verdadero privilegio en la provincia de
              Huesca y muy cerca del Pirineo Aragonés.
            </p>
          </div>
        </b-col>
      </b-row>
      <b-row class="rlv-carrusel_3d">
        <div class="container_3d">
          <div class="carousel_3d" v-bind:style="style">
            <div class="item_3d a">
              <b-img :src="require('../static/img/rutas/guara01.jpg')" fluid />
            </div>
            <div class="item_3d b">
              <b-img :src="require('../static/img/rutas/guara02.jpg')" fluid />
            </div>
            <div class="item_3d c">
              <b-img :src="require('../static/img/rutas/guara03.jpg')" fluid />
            </div>
            <div class="item_3d d">
              <b-img :src="require('../static/img/rutas/guara04.jpg')" fluid />
            </div>
            <div class="item_3d e">
              <b-img :src="require('../static/img/rutas/guara05.jpg')" fluid />
            </div>
            <div class="item_3d f">
              <b-img :src="require('../static/img/rutas/guara06.jpg')" fluid />
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
            title="Pacos de Moranos. "
            :img-src="require('../static/img/rutas/pacos.png')"
            img-top
            tag="article"
            style=""
            class="rlv-card-rutas-detalles mb-2"
          >
            <b-card-text>
              El itinerario discurre por ambientes muy diversos, desde paisajes
              humanizados donde olivos, almendros y campos de labor indican
              todavía la presencia humana, para después pasar entre pinares de
              pino silvestre, que son los más meridionales del Parque Natural y
              del Alto Aragón, finalmente, por zonas de grandes paredes rocosas
              donde viven especies rupícolas de gran interés. En definitiva, un
              recorrido muy interesante que ofrece al naturalista un amplio
              abanico de posibilidades en cuanto a la observación de especies,
              tanto animales como vegetales. En el núcleo urbano de Morrano,
              junto a la parada del autobús, se inicia el sendero que recorre el
              pueblo tomando la calle de la izquierda hasta encontrar una senda
              que parte de una pequeña plaza. El comienzo del camino es paralelo
              a unos campos de cultivo y enseguida cruza la carretera para
              continuar por la senda que conduce a los Pacos de Morrano, hasta
              llegar al farallón rocoso denominado “El Huevo”. 
            </b-card-text>
          </b-card>
        </b-col>
        <b-col cols="12" md="6" lg="4">
          <b-card
            title="El huevo de San Cosme."
            :img-src="require('../static/img/rutas/huevo.png')"
            img-top
            tag="article"
            style=""
            class="rlv-card-rutas-detalles mb-2"
          >
            <b-card-text>
              San Cosme es un eremitorio que cuenta con un conjunto de ermitas,
              algunas de ellas en estado ruinoso, entre las que destaca la
              rupestre que le da nombre, ubicada al abrigo de una impresionante
              visera rocosa y adosada al conjunto de la casa del ermitaño y la
              casa palacio de los Duques de Villahermosa. Por otra parte,
              Vadiello es lugar idóneo para ver el distinto efecto de la erosión
              sobre el conglomerado (Mallos de Ligüerri, San Cosme, El Huevo) y
              la caliza (Pico del Borón, Fragineto). Es zona de nidificación de
              numerosas aves rupícolas, por lo que es fácil la observación de
              especies como el quebrantahuesos, buitre leonado o alimoche, y
              enclave con una excelente representación de carrascal
              mediterráneo.
            </b-card-text>
          </b-card>
        </b-col>
        <b-col cols="12" md="6" lg="4">
          <b-card
            title="Sierra de Bonés."
            :img-src="require('../static/img/rutas/sierra-bones.png')"
            img-top
            tag="article"
            style=""
            class="rlv-card-rutas-detalles mb-2"
          >
            <b-card-text>
              El itinerario se enmarca en una espectacular y poco conocida zona
              del entorno del Parque Natural, acercando al visitante a un
              territorio de contrastes, donde la solana está dominada por
              matorral de boj y quejigar, mientras que en la umbría aparece un
              bosque mixto de haya y pino silvestre. Además, se puede disfrutar
              de las magníficas praderas que se encuentran en la cabecera del
              río Flumen, compartimentadas por características cercas de piedra.
              El sendero finaliza en la ermita de la Magdalena, que data de los
              siglos XVI a XVIII y que en la actualidad es usada como refugio de
              pastores.
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
          if (data.activity[i].title === config.rutaVueloName) {
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
