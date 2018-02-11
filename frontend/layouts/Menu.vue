<template >
<v-app id="sandbox" :dark="dark" :light="!dark" standalone>
  <v-navigation-drawer v-model="primaryDrawer.model" persistent='persistent' dark>
    <v-list dense>
      <v-list-group v-for="item in items" :value="item.active" v-bind:key="item.title">
          <v-list-tile slot="item" @click="" >
            <v-list-tile-action>
              <v-icon>{{ item.icon }}</v-icon>
              </v-list-tile-action>
              <v-list-tile-content>
                <v-list-tile-title>{{ item.title }}</v-list-tile-title>
              </v-list-tile-content>
              <v-list-tile-action>
                <v-icon>keyboard_arrow_downc  </v-icon>
              </v-list-tile-action>
          </v-list-tile >
          <v-list-tile v-for="subItem in item.items" v-bind:key="subItem.title" >
              <v-list-tile-content>
                <v-list-tile-title>{{ subItem.title }}</v-list-tile-title>
               </v-list-tile-content>
              <!--<v-list-tile-action>
                <v-icon>{{ subItem.action }}</v-icon>
              </v-list-tile-action>-->
          </v-list-tile>
      </v-list-group>
        <v-list-tile @click.native="logout">
          <v-list-tile-action>
            <v-icon> exit_to_app</v-icon> 
          </v-list-tile-action>
          <v-list-tile-content>
          <v-list-tile-title> Salir</v-list-tile-title>
        </v-list-tile-content>
        </v-list-tile>
    </v-list>
  </v-navigation-drawer>    
  <v-toolbar fixed>
    <v-toolbar-side-icon @click.native.stop="primaryDrawer.model = !primaryDrawer.model" v-if="primaryDrawer.type !== 'permanent'"></v-toolbar-side-icon>
    <v-toolbar-title> {{ title }}</v-toolbar-title>
  </v-toolbar fixed>
  <main>
    <v-container fluid mb-5 pt-0>
      .nuxt
    </v-container >
   </main> 
  <v-footer fixed>
    <span> © {{ new Date().getFullYear() }} </span> Jose Luis Cáceres Escudero
  </v-footer fixed>
</v-app>
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
          {
            icon: 'local_activity',
            title: 'Usuario',
            items: [
              { title: 'Cliente' },
              { title: 'Tecnico' },
              { title: 'Administrador' },
            ]
          },
          {
            icon: 'local_activity',
            title: 'Vehiculo',
            items: [
              { title: 'Motocicleta' },
              { title: 'Tipo Motocicleta' },
              { title: 'Marca' },
            ]
          },
          {
            icon: 'local_activity',
            title: 'Taller',
            items: [
              { title: 'Orden Entrada' },
              { title: 'Orden Salida' },
              { title: 'Servicio Taller' },
              { title: 'Tabla Mantenimiento' },
              { title: 'Manual Servicio' },
            ]
          }
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