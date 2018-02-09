<template>
  <v-card class="grey lighten-4 elevation-0">
    <v-card-text>
      <v-container fluid>
        <v-layout row>
          <v-flex xs4>
            <v-subheader>Nombre</v-subheader>
          </v-flex>
          <v-flex xs8>
            <v-text-field label="Escriba su nombre" v-model="nombre"></v-text-field>
          </v-flex>
        </v-layout>
        <v-layout row>
          <v-flex xs4>
            <v-subheader>Moto</v-subheader>
          </v-flex>
          <v-flex xs8>
            <v-text-field label="Escriba el modelo de su moto" v-model="moto"></v-text-field>
          </v-flex>
        </v-layout>
        <v-layout row>
          <v-flex xs8>
            <v-btn primary class="pink" dark @click.native="imprimir">Imprimir</v-btn>
          </v-flex>
        </v-layout>
      </v-container>
    </v-card-text>
  </v-card>
</template>

<style scoped>
</style>

<script>
export default {
  data () {
    return {
      nombre: null,
      moto: null
    }
  },
  methods: {
    imprimir () {
      console.log(this.nombre);
      console.log(this.moto);
    }
  }
}
</script>
