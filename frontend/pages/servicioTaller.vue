<template>
  <v-container fluid>
    <v-layout row wrap>
      <v-flex xs12 md6 lg12 offset-md3>
        <v-card>
          <v-toolbar color="red" dark>
            <v-toolbar-title>Servicio Taller</v-toolbar-title>
          </v-toolbar>
          <v-card-text>
            <span class="title">Información personal</span>
            <v-text-field
              label="Servicio"
              class="mt-5"
              v-model="servicio"
              required
            ></v-text-field>
            
            
            <small>*Estos campos son requeridos</small>
          </v-card-text>
        </v-card>
        
        <v-flex xs8>
            <v-btn primary class="blue" dark @click.native="guardar">Guardar</v-btn>
            <v-btn primary class="green" dark @click.native="buscar">Buscar</v-btn>
          </v-flex>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<style scoped>
</style>

<script>
export default {
  data () {
    return {
      servicio:null,
    }
  },
  methods: {
    guardar () {
    },
    buscar () {
    }
  }
}
</script>