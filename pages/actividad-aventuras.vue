<template>
  <div class="rlv-orientacion">
    <div class="rlv-subnav">
      <b-nav>
        <b-nav-item @click="onOrientacion()" class="rlv-subnav-item" 
          >Curso Orientación</b-nav-item
        >
        <b-nav-item  @click="onSenderismo()" class="rlv-subnav-item"
          >Senderismo</b-nav-item
        >
        <b-nav-item @click="onAventuras()" class="rlv-subnav-item" active
          >Aventuras
        </b-nav-item>
        <b-nav-item @click="onMicologia()" class="rlv-subnav-item"
          >Curso de Micología
        </b-nav-item>        
      </b-nav>
    </div>
  </div>
</template>
<script>
export default {
  methods: {
    onOrientacion() {
      this.$router.push('/actividad-orientacion')
    },
    onSenderismo() {
      this.$router.push('/actividad-senderismo')
    },
    onAventuras() {
      this.$router.push('actividad-aventuras')
    },
    onMicologia() {
      this.$router.push('/actividad-micologia')
    },
    
  }
}
</script>