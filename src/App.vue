<template lang="pug">
#app.app
  Header
  .contenedor-principal
    AsideMenu
    section.seccion-principal(:class="{'seccion-principal--barra-avance-open' : !menuState}")
      router-view
  BarraAvance
  Accesibilidad
</template>

<script>
export default {
  name: 'App',
  data: () => ({
    menuOpen: false,
  }),
  computed: {
    menuState() {
      return this.$store.getters.isMenuOpen
    },
  },
  mounted() {
    this.$aos.init({
      offset: 100,
    })
  },
}
</script>
<style lang="sass">
.banner-interno
  height: 114px
.banner-interno__fondo
  background-image: url(assets/curso/fondo_tema.png) !important
.banner-principal .tarjeta
  background-position: inherit !important
.titulo-principal__numero
  background-color: #FFC721 !important
.titulo-principal__numero span
  color: #12263F !important
.curso-main-container > .container
  overflow-x: clip !important
.titulo-segundo:after
  border-left-color: #FFC721 !important
.banner-principal-decorativo-1
  top: 15% !important
  right: 72% !important
  -webkit-animation: float1 3.5s ease-in-out infinite alternate
  animation: float1 3.5s ease-in-out infinite alternate
.banner-principal-decorativo-2
  top: 67% !important
  right: 5% !important
  -webkit-animation: float1 3.5s ease-in-out infinite alternate
  animation: float1 3.5s ease-in-out infinite alternate
.d-none.d-lg-block.col-lg-5.px-0.banner-principal__img
  padding-bottom: 0px !important
  text-align: center
  padding-right: 0px !important
.banner-interno__titulo h1, .banner-interno__titulo h2, .banner-interno__titulo h3, .banner-interno__titulo h4, .banner-interno__titulo h5, .banner-interno__titulo h6
  color: #12263f !important
.banner-interno__titulo__icono
  background-color: #12263f !important
.d-none.d-lg-block.col-lg-5.px-0.banner-principal__img img
  max-width: 280px
  display: inline
  margin-bottom: -6px
</style>
