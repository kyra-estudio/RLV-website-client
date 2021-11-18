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
            id="name"
            type="text"
            
            placeholder="Nombre y Apellidos"
            required
          ></b-form-input>
        </b-col>
      </b-row>
      <b-row class="mt-4 row justify-content-center">
        <b-col sm="10">
          <b-form-file placeholder="Fotografía" required></b-form-file>
        </b-col>
      </b-row>
      <b-row class="mt-4 row justify-content-center">
        <b-col sm="10">
          <b-form-input
            id="name"
            type="email"
            
            placeholder="e-mail"
            required
          ></b-form-input>
        </b-col>
      </b-row>
      <b-row class="mt-4 row justify-content-center">
        <b-col sm="10">
          <b-form-input
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
            id="password2"
            type="password"
            
            placeholder="Repita contraseña"
            required
          ></b-form-input>
        </b-col>
      </b-row>
      <b-row class="rlv-checkbox mt-1 ">
        <b-form-checkbox
          id="checkbox-1"
          v-model="status"
          name="checkbox-1"
          value="accepted"
          unchecked-value="not_accepted"
        >
          Acepto los términos y condiciones
        </b-form-checkbox>
      </b-row>

      <b-row class="mt-4 row justify-content-center">
        <b-button class="rlv-btn-form" size="lg">Registrar </b-button>
      </b-row>
    </b-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      avatar: undefined,
      valid: true,
      password: '',
      password2: '',
      email: '',
      status: 'not_accepted',
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
      formData.append('avatar', this.avatar)
      formData.append('email', this.email)
      formData.append('password', this.password)
      try {
        const res = await fetch('http://localhost:4500/api/user/signUp', {
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
