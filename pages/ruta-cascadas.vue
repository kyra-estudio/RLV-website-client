<template>
  <div class="rlv-ruta-cascadas">
    <div class="rlv-subnav">
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
        <b-nav-item @click="onVuelo()" class="rlv-subnav-item"
          >Vista a vuelo de pájaro
        </b-nav-item>
        <b-nav-item @click="onCascadas()" class="rlv-subnav-item" active
          >Ruta entre cascadas y saltos de agua
        </b-nav-item>
      </b-nav>
    </div>
    <b-container>
      <b-row class="rlv-ruta-detalle">
        <b-col cols="12" md="12" lg="8">
          <div class="rlv-imagen-ruta-detalle">
            <b-img
              :src="require('../static/img/rutas/ruta-cascadas-xl.png')"
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
              La Sierra del Rincón es un sistema montañoso español que se
              encuentra entre las sierras de Ayllón y Guadarrama, en la comarca
              de la Sierra Norte en el extremo nororiental de la Comunidad de
              Madrid. Se extiende por los municipios de: La Hiruela, Horcajuelo
              de la Sierra, Montejo de la Sierra, Prádena del Rincón y Puebla de
              la Sierra. Fue declarada Reserva de la Biosfera en junio de 2005
              por la UNESCO.
            </p>
            <p>
              La Sierra del Rincón en su ubicación entre los relieves de las
              sierras de Guadarrama y Ayllón, tiene su reflejo en la
              singularidad de este territorio y en su naturaleza, con unos
              ecosistemas excepcionales, por su la elevada diversidad de
              hábitats: pinares, robledales, encinares, hayedos, pastizales,
              piornales y matorrales.
            </p>
          </div>
        </b-col>
      </b-row>
      <b-row class="rlv-carrusel_3d">
        <div class="container_3d">
          <div class="carousel_3d" v-bind:style="style">
            <div class="item_3d a">
              <b-img
                :src="require('../static/img/rutas/sierramadrid01.jpg')"
                fluid
              />
            </div>
            <div class="item_3d b">
              <b-img
                :src="require('../static/img/rutas/sierramadrid02.jpg')"
                fluid
              />
            </div>
            <div class="item_3d c">
              <b-img
                :src="require('../static/img/rutas/sierramadrid03.jpg')"
                fluid
              />
            </div>
            <div class="item_3d d">
              <b-img
                :src="require('../static/img/rutas/sierramadrid04.jpg')"
                fluid
              />
            </div>
            <div class="item_3d e">
              <b-img
                :src="require('../static/img/rutas/sierramadrid05.jpg')"
                fluid
              />
            </div>
            <div class="item_3d f">
              <b-img
                :src="require('../static/img/rutas/sierramadrid06.jpg')"
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
            title="La Hiruela. "
            :img-src="require('../static/img/rutas/hiruela.png')"
            img-top
            tag="article"
            style=""
            class="rlv-card-rutas-detalles mb-2"
          >
            <b-card-text>
              La Hiruela es uno de los pueblos más bonitos y mejor conservados
              de la Comunidad de Madrid. Sus calles apenas han cambiado desde el
              siglo XVIII. Desde la entrada al municipio hasta la plaza
              principal donde está la iglesia de San Miguel puedes caminar por
              dos vías paralelas en las que observar sus típicas casas,
              construidas en piedra, adobe y madera de roble (materiales que
              obtenían de la propia Sierra). Los oficios de la vida. 2,7
              kilómetros. Permite conocer los sitios que ejemplifican las que
              fueran las claves de sustento económico de La Hiruela: el molino
              harinero, el colmenar tradicional y la carbonera. En el colmenar,
              cuya antigüedad dicen que data de más de 200 años, es muy curioso
              ver las colmenas tradicionales, realizadas en troncos de roble
              huecos. También interesante es la recreación de una antigua
              carbonera vegetal de roble: La Hiruela vendía carbón hasta 1950 a
              los municipios de alrededor e incluso a la capital madrileña. Todo
              con sus correspondientes paneles informativos, muy de agradecer.
            </b-card-text>
          </b-card>
        </b-col>
        <b-col cols="12" md="6" lg="4">
          <b-card
            title="Montejo de la sierra."
            :img-src="require('../static/img/rutas/montejo.png')"
            img-top
            tag="article"
            style=""
            class="rlv-card-rutas-detalles mb-2"
          >
            <b-card-text>
              Montejo de la Sierra se encuentra englobado dentro de la zona
              conocida como Sierra del Rincón, catalogada en la actualidad por
              la UNESCO como Reserva de la Biosfera. Al igual que el resto de
              los municipios integrados en la Reserva, Montejo es conocido por
              sus valores naturales y culturales, y por reunir un número
              importante de recursos turísticos. mediterráneo. Existe una
              historia que cuenta que en el que hoy es Hayedo de Montejo,
              habitaban varios duendes y hadas que atraían a visitantes para
              convertirlos en animales y así embellecer el bosque de El
              Chaparral (como se llamaba antiguamente). En el año 1460 el pueblo
              compró este bosque a un noble de Sepúlveda. Al principio hubo
              discusión por decidir a quién pertenecía el territorio pero
              cuentan que el Emperador Carlos I de España y V de Alemania
              defendió que el monte pertenecía a Montejo.
            </b-card-text>
          </b-card>
        </b-col>
        <b-col cols="12" md="6" lg="4">
          <b-card
            title="Hayedo de Montejo."
            :img-src="require('../static/img/rutas/hayedo.png')"
            img-top
            tag="article"
            style=""
            class="rlv-card-rutas-detalles mb-2"
          >
            <b-card-text>
              Fue declarado Sitio Natural de Interés Nacional en 1974. El
              microclima existente en la zona debido a la captación de humedad
              proveniente de las masas de aire que no chocan contra la sierra, y
              el hecho de que la ladera de la colina permanezca en umbría, han
              hecho posible que se conserve el hayedo, más propio de
              Centroeuropa, existente en Montejo desde épocas postglaciales. El
              hayedo representa los restos de la vegetación caducifolia
              centroeuropea en España. Es uno de los más estudiados de la
              península ibérica, y la gran afluencia de personas ha hecho que
              las visitas estén restringidas. La única forma de visitar el
              hayedo de Montejo es a través de las visitas guiadas que gestiona
              el centro de recursos de la sierra del Rincón. En 2017, junto con
              otros hayedos de España y Europa, fue declarado Patrimonio de la
              Humanidad por la Unesco como extensión de los Hayedos primarios de
              los Cárpatos y otras regiones de Europa
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
          if (data.activity[i].title === config.rutaCascadasName) {
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
