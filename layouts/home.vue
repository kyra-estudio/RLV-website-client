<template>
  <div class="RLV-layout-default">
    
      <RLVNavBar :noHome="false" />
      <main>
        <!-- <b-container> -->
          <Nuxt />
        <!-- </b-container> -->
      </main>
   
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
