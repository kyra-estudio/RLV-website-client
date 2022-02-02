<template>
  <div class="rlv-sign-in">
    <b-container fluid>
      <div class="rlv-logo-sign-in">
        <b-img
          :src="require('../static/img/signin/logo-signin.png')"
          fluid
        ></b-img>
      </div>

      <b-row class="mt-4 row justify-content-center">
        <b-col sm="6">
          <b-form-input
            v-model="email"
            id="email"
            type="email"
            placeholder="e-mail"
            required
          ></b-form-input>
        </b-col>
      </b-row>
      <b-row class="mt-4 row justify-content-center">
        <b-col sm="6">
          <b-form-input
            v-model="password"
            id="password"
            type="password"
            placeholder="Contraseña"
            required
          ></b-form-input>
        </b-col>
      </b-row>
      <b-row class="mt-4 row justify-content-center">
        <b-button class="rlv-btn-form " size="lg" @click="onSubmit"
          >Entrar
        </b-button>
        <b-button class="ml-5" variant="light" size="lg" href="./sign-up"
          >Registrar
        </b-button>
      </b-row>
    </b-container>
  </div>
</template>
<script>
export default {
  data() {
    return {
      email: '',
      password: '',
    }
  },
  methods: {
    async onSubmit() {
      try {
        const body = JSON.stringify({
          email: this.email,
          password: this.password,
        })

        const res = await fetch('http://localhost:4500/api/user/signIn', {
          method: 'post',
          headers: {
            'Content-Type': 'application/json',
          },
          body,
        })

        const data = await res.json()

        if(res.status.toString() == '409'){
          alert(data)
          return
        }
        
        if (data.err) {
          alert(data.err)
          return
        }
        localStorage.setItem('name', data.name)
        localStorage.setItem('avatar', data.avatar)
        localStorage.setItem('userId', data.id)
        localStorage.setItem('admin', data.admin)
        this.$store.dispatch('user/saveToken', data.token)

        this.$router.push('/inicio')
      } catch (err) {
        alert(err.mesage)
      }
    },
  },
}
</script>
