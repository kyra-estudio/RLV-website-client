<template>
  <div class="rlv-usuarios">
    <b-card header="Usuarios" header-tag="header" class="m-4 text-center">
      <b-row class="rlv-usuarios-container">
        <b-col cols="6" md="6" lg="3" v-for="(user, index) in users" :key="index">
          <b-card class="mt-3">
            <b-card-text>
              <b-avatar :src="user.avatar" size="160" class="mt-2"></b-avatar>
              <h5 class="mt-1">{{ user.name + ' ' + user.lastname }}</h5>
              <b-button
                variant="info"
                class="mb-2"
                @click="removeUser(user._id)"
              >
                <b-icon icon="trash" aria-label="Help"></b-icon>
              </b-button>
              <b-button variant="warning" class="mb-2" v-b-modal="'modal-' + index" @click="getPetitions(user._id)">
                <b-icon icon="chat-square-dots" aria-label="comment"></b-icon>
                <b-modal
                  :id= "'modal-' + index"
                  centered
                  title="Peticiones"
                  header-bg-variant="dark"
                  header-text-variant="light"
                >
                  <div v-for="(petition, petindex) in petitions" :key="petindex">
                    <p>{{petition.date + " - " + petition.activityName}}</p>
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
      users: [],
      petitions: [],
      onFetch: undefined,
    }
  },
  async beforeMount() {
    await this.getUsers()
    this.onFetch = setInterval(async () => {
      await this.getUsers()
    }, 5000)
  },
  destroyed() {
    clearInterval(this.onFetch)
  },
  methods: {
    async getUsers() {
      try {
        const url= config.HOSTNAME + 'api/user/userGetAll'
        const res = await fetch(url, {
          method: 'GET',
        })
        const data = await res.json()
        this.users = data.user
      } catch (err) {
        alert(err.message)
      }
    },
    async removeUser(id) {
      try {
        const body = JSON.stringify({
          userId: id,
        })
        
        const url= config.HOSTNAME + 'api/user/removeUser'

        const res = await fetch(url, {
          method: 'delete',
          headers: {
            'Content-Type': 'application/json',
          },
          body,
        })

        await res.json()

        alert('El usuario se ha eliminado correctamente')
      } catch (err) {
        alert(err.message)
      }
    },
    async getPetitions(userId) {
      try {
        const url = config.HOSTNAME + `api/information/userPetitions/${userId}`
        const res = await fetch(url, {
          method: 'GET',
        })
        const data = await res.json()
        this.petitions = data.informations
      } catch (err) {
        alert(err.message)
      }
    },
  },
}
</script>
  