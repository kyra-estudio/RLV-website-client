<template>
  <div class="rlv-sign-up">
    <b-container fluid>
      <div class="rlv-logo-sign-up">
        <b-img
          :src="require('../static/img/signup/logo-nombre.png')"
          fluid
        ></b-img>
      </div>

      <b-row class="mt-4 row justify-content-center">
        <b-col sm="10">
          <b-form-input
           v-model="name"
            id="name"
            type="text"
            placeholder="Nombre"
            required
          ></b-form-input>
        </b-col>
      </b-row>
      <b-row class="mt-4 row justify-content-center">
        <b-col sm="10">
          <b-form-input
           v-model="lastname"
            id="lastname"
            type="text"
            placeholder="Apellidos"
            required
          ></b-form-input>
        </b-col>
      </b-row>
      <b-row class="mt-4 row justify-content-center">
        <b-col sm="10">
          <b-form-file  v-model="avatar" placeholder="Fotografía" required ></b-form-file>
        </b-col>
      </b-row>
      <b-row class="mt-4 row justify-content-center">
        <b-col sm="10">
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
        <b-col sm="10">
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
        <b-col sm="10">
          <b-form-input
           v-model="password2"
            id="password2"
            type="password"
            placeholder="Repita contraseña"
            required
          ></b-form-input>
        </b-col>
      </b-row>
      <!-- <b-row class="rlv-checkbox mt-1">
        <b-form-checkbox
          id="checkbox-1"
          v-model="status"
          name="checkbox-1"
          value="accepted"
          unchecked-value="not_accepted"
        >
          Acepto los términos y condiciones
        </b-form-checkbox>
      </b-row> -->

      <b-row class="mt-4 row justify-content-center">
        <b-button class="rlv-btn-form" size="lg" @click="onSubmit"
          >Registrar
        </b-button>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import config from '~/config'
export default {
  data() {
    return {
      name: '',
      lastname:"",
      avatar: undefined,
      valid: true,
      password: '',
      password2: '',
      email: '',
      // status: 'not_accepted',
    }
  },
  methods: {
    async onSubmit() {
      if (this.password !== this.password2) {
        alert('Los password deben ser iguales')
        return
      }
      const formData = new FormData()
      formData.enctype = 'multipart/form-data'
      formData.append("name", this.name)
      formData.append("lastname", this.lastname)
      formData.append('avatar', this.avatar)
      formData.append('email', this.email)
      formData.append('password', this.password)
      formData.append('password2', this.password2)
      try {
        const url = config.HOSTNAME + 'api/user/signUp'
        const res = await fetch(url, {
          method: 'POST',
          body: formData,
        })
        const data = await res.json()
        if (data.err) {
          alert(data.err)
        } else {
          this.$router.push('/sign-in')
        }
      } catch (err) {
        alert(err.message)
      }
    },
  },
}
</script>
