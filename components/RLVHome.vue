<template>
  <div class="RLV-home">
    <b-main>
      <b-container class="rlv-main-container">
        <b-row>
          <b-col cols="lg-6">
            <img
              class="rlv-img-claim"
              :src="require('../static/img/home/claim.png')"
              fluid
               width="100%"
              height="auto"
            />
          </b-col>
          <b-col cols="lg-2">
            <h2 class="mb-3 text-lg-right">
              Nunca es tarde para conocer las bellezas de la naturaleza
            </h2>
            <p class="text-lg-right " >
              Todos podemos ver espectaculares fotografías, pero
              <b>¿no preferiríais vivirlas?</b> El tiempo y el esfuerzo que
              requiere ascender una montaña
              <b>no están al alcance de todos.</b> Cuando pisas una cumbre
              puedes estar bastante seguro de que eres de una minoría y de que
              <b>el paisaje que contemplas lo han visto pocos ojos.</b> Los
              senderistas y alpinistas son, por lo general, gente interesante.
              <b>Siempre encontrarás cosas en común para compartir.</b> Son
              positivos, fuertes, confiables y felices de encontrarse en el
              lugar que les arranca sonrisas.<b>
                No pierdas la oportunidad de hacer amigos o unirte a algún grupo
                de montaña. </b
              >El objetivo de todos es el mismo: disfrutar de la belleza que
              ofrecen los espacios salvajes.
            </p>
          </b-col>
          <b-col cols="lg-4">
            <img
              :src="require('../static/img/home/home.png')"
              fluid
              width="100%"
              height="auto"
            />
          </b-col>
        </b-row>
      </b-container>
    </b-main>
  </div>
</template>
<style scoped></style>
