<template>
  <div class="rlv-admin-peticiones">
    <b-row align-v="center">
      <b-col cols="6" class="rlv-zindex d-none d-lg-block">
        <div class="rlv-imagen-sign-up">
          <b-img
            :src="require('../static/img/admin/admin-portada.png')"
            fluid
          ></b-img>
        </div>
      </b-col>
      <b-col cols="6"></b-col>
      
    </b-row>
  </div>
</template>
<script>
export default {
  data() {
    return {
      token: '',
      avatar: undefined,
      name: '',
    }
  },
  //   created() {
  //     if (process.client) {
  //       this.token = localStorage.getItem('token')
  //       this.avatar = localStorage.getItem('avatar')
  //       this.name = localStorage.getItem('name')
  //     }
  //   },
  watch: {
    '$store.state.user.token'(value) {
      if (value) {
        this.token = localStorage.getItem('token')
        this.avatar = localStorage.getItem('avatar')
        this.name = localStorage.getItem('name')
      }
    },
  },
}
</script>
