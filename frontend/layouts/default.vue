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
          { icon: 'settings', text: 'Tipo Moto', to: '/tipoMoto' },
          { icon: 'settings', text: 'Motocicleta', to: '/motocicleta' },
          { icon: 'settings', text: 'Marca Motocicleta', to: '/marca' },
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