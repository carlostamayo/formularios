<template lang="pug">
div(class="hello")
  //- p Contable
  //- g-carousel
  //- g-icon-grid
  //- g-section1
  //- g-section3
  //- g-section4
  //- g-section2
  //- g-section5
  //- g-testimonios
  //- g-contact

</template>

<script>

/*import GCarousel from '~components/GCarousel.vue'
import GIconGrid from '~components/GIconGrid.vue'
import GSection1 from '~components/GSection1.vue'
import GSection2 from '~components/GSection2.vue'
import GSection3 from '~components/GSection3.vue'
import GSection4 from '~components/GSection4.vue'
import GSection5 from '~components/GSection5.vue'
import GTestimonios from '~components/GTestimonios.vue'
import GContact from '~components/GContact.vue'*/


export default {
  data () {
    return {
    }
  },
  layout: 'page',
  components: {
    /*GCarousel,
    GIconGrid,
    GSection1,
    GSection2,
    GSection3,
    GSection4,
    GSection5,
    GTestimonios,
    GContact*/
  },
  head () {
    return {
      meta: [{name: "viewport", content: "width=device-width, initial-scale=1, maximun-scale=1, user-scalable=no, minimal-ui"}],
      title: "Jeromotos"
    }
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="stylus" scoped>

h1, h2
  font-weight normal;

ul
  list-style-type none
  padding 0


li
  display inline-block
  margin 0 10px

a
  color #42b983

</style>


<template lang="pug">
doctype html
v-app(id="sandbox" :dark="dark" :light="!dark" standalone)
  v-navigation-drawer(v-model="primaryDrawer.model" persistent='persistent' dark)
    v-list(dense)
      template(v-for="(item, i) in items")
        v-list-tile(:key="i" nuxt link :to="item.to")
          v-list-tile-action
            v-icon(dark) {{ item.icon }}

          v-list-tile-content
            v-list-tile-title {{ item.text }}

      v-list-tile(@click.native="logout")
        v-list-tile-action
          v-icon(dark) exit_to_app

        v-list-tile-content
          v-list-tile-title Salir

  v-toolbar(fixed)
    v-toolbar-side-icon(@click.native.stop="primaryDrawer.model = !primaryDrawer.model" v-if="primaryDrawer.type !== 'permanent'")
    v-toolbar-title {{ title }}

  main
    v-container(fluid mb-5 pt-0)
      nuxt

  v-footer(fixed)
    <span> © {{ new Date().getFullYear() }} </span> Jose Luis Cáceres Escudero

</template>

<script>
  export default {
    data: () => {
      return {
        dark: false,
        primaryDrawer: {
          model: true,
          type: 'persistent',
          clipped: false,
          floating: true,
          mini: false
        },
        footer: {
          fixed: true
        },
        items: [
          { icon: 'settings', text: 'Mantenimiento', to: '/mantenimiento' },
          { icon: 'person', text: 'Usuarios', to: '/usuarios' },
          { icon: 'person', text: 'Roles', to: '/roles' },
          { icon: 'settings', text: 'PruebaMenu', to: '/pruebamenu' },
         ],
        title: 'Administración Jeromotos'
      }
    },
    methods: {
      logout () {
        sessionStorage.removeItem("x-access-token")
        this.$router.push('/')
      }
    }
  }
</script>

<style lang="stylus" scoped>

#sandbox
  border 1px solid rgba(0, 0, 0, .25)
  overflow hidden

</style>
