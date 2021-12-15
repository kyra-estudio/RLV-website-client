<template>
  <div class="rlv-familia">
    <div class="rlv-subnav">
      <b-nav>
        <b-nav-item @click="onCarneros()" class="rlv-subnav-item" 
          >Ruta de los carneros salvajes</b-nav-item
        >
        <b-nav-item active @click="onFamilia()" class="rlv-subnav-item"
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
                <p class="sure" @click="goSignUp()" v-if="!token">Regístrate!</p>
                <p class="sure" @click="goSignUp()" v-if="token">+ info!  </p>  
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
  },
  
}
</script>
