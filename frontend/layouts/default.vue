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

  v-toolbar(fixed class="grey darken-2 white--text ")
    v-toolbar-side-icon(@click.native.stop="primaryDrawer.model = !primaryDrawer.model" v-if="primaryDrawer.type !== 'permanent'")
    v-toolbar-title {{ title }}
    <v-spacer></v-spacer>
    <v-btn icon>
            <v-icon>search</v-icon>
    </v-btn>
  main
    v-container(fluid mb-5 pt-0)
      nuxt

  v-footer(fixed)
    <span> © {{ new Date().getFullYear() }} </span> Joiner Sánchez & Carlos Tamayo

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
          { icon: 'build', text: 'Orden de Trabajo', to: '/ordenTrabajo' },
          { icon: 'build', text: 'Agregar Orden de Trabajo', to: '/agregarOrdenTrabajo' },
          { icon: 'person', text: 'Usuarios', to: '/usuarios' },
          { icon: 'motorcycle', text: 'Tipo Moto', to: '/tipoMoto' },
          { icon: 'motorcycle', text: 'Motocicleta', to: '/motocicleta' },
          { icon: 'build', text: 'Servicio Taller', to: '/serviciotaller' },
          { icon: 'motorcycle', text: 'Marca', to: '/marca' },
          { icon: 'build', text: 'Tabla Mantenimiento', to: '/tablaMantenimiento' },
          { icon: 'person', text: 'Prueba', to: '/prueba' },
          { icon: 'person', text: 'Prueba Data', to: '/pruebaDataTable' },
         ],
        title: 'Administración Jeromotos',
        icono:"build"
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