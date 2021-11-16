<template>
  <div class="RLV-layout-default">
    <v-app>
      <RLVNavBar :noHome="false" />
      <v-main>
        <v-container>
          <Nuxt />
        </v-container>
      </v-main>
    </v-app>
  </div>
</template>

<script>
export default {
  // beforeMount() {
  //   const token = localStorage.getItem('token')
  //   if (token) {
  //     this.$store.commit('user/setToken', token)
  //   }
  // },
  // watch: {
  //   '$store.state.user.token'(value) {
  //     if (!value) {
  //       this.$router.push('/sign-in')
  //     }
  //   },
  // },
}
</script>
