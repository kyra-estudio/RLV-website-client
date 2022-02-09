<template>
  <div class="rlv-admin-usuarios">
    <b-row>
      <b-col cols="6" class="rlv-zindex d-none d-lg-block">
        <div class="">
          <b-img
            :src="require('../static/img/admin/admin-portada.png')"
            fluid
          ></b-img>
        </div>
      </b-col>
      <b-col cols="12" md="12" lg="6">
     <RLVUsuarios class="mt-4" />
     </b-col>
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
