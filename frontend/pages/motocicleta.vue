<template>
  <v-container fluid >
    <v-layout row wrap>
      <v-flex xs12 md6 offset-md3 >
        <v-card>
          <v-toolbar color="red" dark>
            <v-toolbar-title>Motocicleta</v-toolbar-title>
          </v-toolbar>
          <v-card-text>
            <span class="title">Información personal</span>
            <v-text-field
              label="Placa"
              v-model="placa"
              required
            ></v-text-field>
            <v-text-field
              label="Color"
              v-model="color"
              required
            ></v-text-field>
            <v-select
             label="Referencia"
             v-model="referencia"
            :items="items"
            :error-messages="selectErrors"
            @change="$v.select.$touch()"
            @blur="$v.select.$touch()"
            required
            ></v-select>
            <v-text-field
              label="Propietario"
              v-model="propietario"
              required
            ></v-text-field>
            <v-text-field
              label="Km Promedio Diario"
              v-model="promedio"
              disabled nofocus
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
      placa:null,
      color:null,
      referencia:null,
      propietario:null,
      promedio:0
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