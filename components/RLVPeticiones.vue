<template>
  <div class="rlv-peticiones">
    <b-card header="Peticiones" header-tag="header" class="m-4 text-center">
      <b-row class="rlv-peticiones-container">
        <b-col
          cols="12"
          v-for="(information, index) in informations"
          :key="index"
        >
          <b-card class="mt-3">
            <b-card-text>
              <h3 class="mt-1">{{ information.activityName }}</h3>
              <h4>{{ information.user.name }}</h4>

              <b-button variant="info" class="mb-2" v-b-modal = "'modal-center-' + index">
                <b-icon icon="clipboard-data" aria-label="Help"></b-icon>
                <b-modal
                  :id="'modal-center-' + index"
                  centered
                  title="Detalle de la petición"
                  header-bg-variant="dark"
                  header-text-variant="light"
                >
                  <p class="my-2">
                    <strong>Actividad:</strong> {{ information.activityName }}
                  </p>
                  <p class="my-2">
                    <strong>Usuario:</strong> {{ information.user.name }}
                  </p>
                  <p class="my-2">
                    <strong>email:</strong> {{ information.user.email }}
                  </p>
                  <p class="my-2">
                    <strong>Teléfono:</strong> {{ information.tel }}
                  </p>
                  <p class="my-2">
                    <strong>Fecha de la Actividad:</strong>
                    {{ information.date }}
                  </p>
                  <p class="my-2">
                    <strong>Nº adultos:</strong> {{ information.adult }}
                  </p>
                  <p class="my-2">
                    <strong>Nº niños:</strong> {{ information.children }}
                  </p>
                  <p class="my-2">
                    <strong>Comentarios:</strong> {{ information.comment }}
                  </p>
                </b-modal>
              </b-button>
              <b-button variant="secondary" class="mb-2" v-b-modal="'modal-email-' + index">
                <b-icon icon="envelope" aria-label="email"></b-icon>
                <b-modal
                  :id="'modal-email-' + index"
                  centered
                  title="email"
                  header-bg-variant="dark"
                  header-text-variant="light"
                >
                  <b-form-textarea
                    id="textarea"
                    v-model="message"
                    placeholder="Enter something..."
                    rows="3"
                    max-rows="6"
                  ></b-form-textarea>
                  <b-button
                    variant="dark"
                    class="mb-2"
                    @click="
                      sendEmail(
                        information.user.email,
                        information.activityName
                      )
                    "
                  >
                    <b-icon
                      icon="arrow-right-square-fill"
                      aria-label="send"
                    ></b-icon>
                  </b-button>
                </b-modal>
              </b-button>
              <b-button variant="warning" class="mb-2" v-b-modal="'modal-comment-' + index" @click="getComments(information._id)">
                <b-icon icon="chat-square-dots" aria-label="comment"></b-icon>
                <b-modal
                  :id="'modal-comment-' + index"
                  centered
                  title="Comentarios"
                  header-bg-variant="dark"
                  header-text-variant="light"
                  ok-only
                >
                  <div v-for="(comment, comindex) in comments" :key="comindex">
                    <p>{{comment.date + " - " + comment.comment}}</p>
                  </div>
                  <div>
                    <b-form-input
                    id="date"
                    name="date"
                    type="date"
                    class="form-control"
                    v-model="date"
                    required
                  />
                  <b-form-textarea
                    id="textarea"
                    v-model="comment"
                    placeholder="Enter something..."
                    rows="3"
                    max-rows="6"
                  ></b-form-textarea>
                  <b-button variant="dark" class="mb-2" @click="commentAdmin(information._id)">
                    <b-icon
                      icon="arrow-right-square-fill"
                      aria-label="send"
                    ></b-icon>
                  </b-button>
                  </div>
                </b-modal>
              </b-button>
            </b-card-text>
          </b-card>
        </b-col>
      </b-row>
    </b-card>
  </div>
</template>
<script>
import config from '~/config'
export default {
  data() {
    return {
      informations: [],
      onFetch: undefined,
      message: '',
      date: "",
      comment:"",
      comments:[],

    }
  },
  async beforeMount() {
    await this.getPetitions()
    this.onFetch = setInterval(async () => {
      await this.getPetitions()
    }, 5000)
  },
  destroyed() {
    clearInterval(this.onFetch)
  },
  methods: {
    async getPetitions() {
      try {
        const url = config.HOSTNAME + 'api/information/allPetition'
        const res = await fetch(url, {
          method: 'GET',
        })
        const data = await res.json()
        this.informations = data.informations
      } catch (err) {
        alert(err.message)
      }
    },
    async sendEmail(email, activity) {
      try {
        const url = config.HOSTNAME + 'api/email/send-email'
        const body = JSON.stringify({
          email: email,
          activity: activity,
          message: this.message,
        })
        const res = await fetch(url, {
          method: 'post',
          headers: {
            'Content-Type': 'application/json',
          },
          body,
        })
        await res
        alert('El email se envio correctamente')
      } catch (err) {
        alert(err.message)
      }
    },
    async commentAdmin(informationId) {
      try {
        const url = config.HOSTNAME + 'api/comment/createComment'
        const body = JSON.stringify({
          date: this.date,
          comment: this.comment,
          informationId: informationId,
        })
        const res = await fetch(url, {
          method: 'post',
          headers: {
            'Content-Type': 'application/json',
          },
          body,
        })
        const data = await res.json()
        console.log(data)
        if (data.err) {
          alert(data.err)
        }
        else{
          alert('comentario guardado correctamente')
        }
      } catch (err) {
        alert(err.message)
      }
    },
    async getComments(informationId) {
      try {
        const url = config.HOSTNAME + `api/comment/detailsComment/${informationId}`
        const res = await fetch(url, {
          method: 'GET',
        })
        const data = await res.json()
        this.comments = data.completeComment
      } catch (err) {
        alert(err.message)
      }
    },
  },
}
</script>
