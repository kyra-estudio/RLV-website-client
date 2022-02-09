<template>
  <div class="rlv-formulario">
    <b-row>
      <b-col lg="6">
        <b-carousel
          id="carousel-2"
          v-model="slide"
          :interval="4000"
          @sliding-start="onSlideStart"
          @sliding-end="onSlideEnd"
        >
          <b-carousel-slide>
            <template #img>
              <img
                class="d-block img-fluid w-100"
                :src="require('../static/img/peticiones/escalada1.png')"
                fluid /></template
          ></b-carousel-slide>
          <b-carousel-slide>
            <template #img>
              <img
                class="d-block img-fluid w-100"
                :src="require('../static/img/peticiones/senderismo1.png')"
                fluid
                alt="image slot" /></template
          ></b-carousel-slide>
          <b-carousel-slide>
            <template #img>
              <img
                class="d-block img-fluid w-100"
                :src="require('../static/img/peticiones/micologia1.png')"
                fluid /></template
          ></b-carousel-slide>

          <b-carousel-slide>
            <template #img>
              <img
                class="d-block img-fluid w-100"
                :src="require('../static/img/peticiones/rafting1.png')"
                fluid /></template
          ></b-carousel-slide>
          <b-carousel-slide>
            <template #img>
              <img
                class="d-block img-fluid w-100"
                :src="require('../static/img/peticiones/escalada2.png')"
                fluid /></template
          ></b-carousel-slide>
          <b-carousel-slide>
            <template #img>
              <img
                class="d-block img-fluid w-100"
                :src="require('../static/img/peticiones/senderismo2.png')"
                fluid /></template
          ></b-carousel-slide>
        </b-carousel>
      </b-col>
      <b-col lg="6">
        <h1 class="rlv-form-title">{{ activityName }}</h1>
        <h5 class="text-center">Rellena tus datos y te llamamos gratis</h5>

        <b-col md="8" offset-md="2" class="rlv-form">
          <div class="form-group">
            <label class="control-label" for=""
              >Ingrese la fecha en la que desea realizar la actividad</label
            >
            <div class="">
              <b-form-input
                id="date"
                name="date"
                type="date"
                class="form-control"
                v-model="date"
                required
              />
            </div>
          </div>
          <div class="form-group">
            <label class="control-label" for=""
              >Ingrese el número de adultos</label
            >
            <div class="">
              <b-form-input
                v-model="adult"
                id="adult"
                name="adult"
                type="number"
                class="form-control"
                min="0"
                max="16"
                required
              />
            </div>
          </div>
          <div class="form-group">
            <label class="control-label" for=""
              >Ingrese el número de menores de 12 años</label
            >
            <div class="">
              <b-form-input
                v-model="children"
                id="children"
                name="children"
                type="number"
                class="form-control"
                min="0"
                max="16"
                required
              />
            </div>
          </div>
          <div class="form-group">
            <label class="control-label" for=""
              >Ingrese el número de telefono
            </label>
            <div class="">
              <b-form-input
                v-model="tel"
                id="telf"
                name="telf"
                type="tel"
                class="form-control"
                maxlength="9"
                required
              />
            </div>
          </div>
          <div>
            <b-form-textarea
              v-model="comment"
              id="textarea"
              placeholder="comentarios"
              rows="3"
              max-rows="6"
            ></b-form-textarea>
          </div>
          <div class="col text-center">
            <b-button class="rlv-btn-form mt-3" size="lg" @click="onSubmit"
              >Enviar petición
            </b-button>
          </div>
        </b-col>
      </b-col>
    </b-row>
  </div>
</template>

<script>
import config from '~/config'
export default {
  data() {
    return {
      slide: 0,
      sliding: null,
      activityId: '',
      userId: '',
      activityName: '',
      date: '',
      adult: '',
      children: '',
      tel: '',
      comment: '',
    }
  },
  beforeMount() {
    this.loadData()
  },
  methods: {
    loadData() {
      this.activityId = this.token = localStorage.getItem('activityId')
      this.activityName = this.token = localStorage.getItem('activityName')
      this.userId = this.token = localStorage.getItem('userId')
    },

    async onSubmit() {
      try {
        const url = config.HOSTNAME + 'api/information/createPetition'
        const body = JSON.stringify({
          activityId: this.activityId,
          userId: this.userId,
          date: this.date,
          adult: this.adult,
          children: this.children,
          tel: this.tel,
          comment: this.comment,
        })
        const res = await fetch(
          url,
          {
            method: 'post',
            headers: {
              'Content-Type': 'application/json',
            },
            body,
          }
        )

        const data = await res.json()

        if (res.status.toString() == '409') {
          alert(data)
          return
        }

        if (data.err) {
          alert(data.err)
          return
        }
        alert(
          'El formulario se ha enviado correctamente, en breve nos pondremos en contacto con Usted'
        )
        ;(this.date = ''),
          (this.adult = ''),
          (this.children = ''),
          (this.tel = ''),
          (this.comment = '')
      } catch (err) {
        alert(err.mesage)
      }
    },
    onSlideStart(slide) {
      this.sliding = true
    },
    onSlideEnd(slide) {
      this.sliding = false
    },
  },
}
</script>
