<template>
    <div class="rlv-signUp">
        <b-row>
        <b-col class="rlv-zindex d-none d-lg-block">
          <div class="rlv-imagen-sign-up">
        <b-img :src="require('../static/img/signup/signup.png')" fluid ></b-img>
      </div>
        </b-col>
        <b-col>
            <RLVSignUp />
        </b-col>
        </b-row>
    </div>
</template>

<script>
export default {
  
  data() {
    return {
      isValid: true,
    }
  },
  asyncData(ctx) {
    if (ctx?.store?.state?.user?.token && ctx?.store?.state?.user?.token != 'undefined') {
      ctx.redirect('/home')
    }
  },
  created() {
    if (process.client) {
      const token = localStorage.getItem('token')
      if (token) {
        this.$router.push('/home')
      } else {
        // this.isValid = true
      }
    }
  },
  computed: {
    token() {
      return this.$store.state.user.token
    },
  },
}
</script>
