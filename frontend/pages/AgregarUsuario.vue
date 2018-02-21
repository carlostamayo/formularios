<template>
  <v-container fluid>
    <v-layout row wrap>
      <v-flex xs12>
        <v-card>
          <v-toolbar class="indigo" dark>
            <v-toolbar-title class="display">Datos de usuario</v-toolbar-title>
          </v-toolbar>
          <v-container fluid>
            <v-layout row>
              <v-flex xs1></v-flex>
              <v-flex xs2>
                <v-text-field
                    
                    class="subheading"
                    label="Cedula"
                ></v-text-field>
              </v-flex>
          <v-flex xs2></v-flex>
          <v-flex xs6>
            <!--<v-select v-bind:items="[{ text: 'Mobile' }]" label="Mobile" dark></v-select>-->
            <v-text-field
              label="Nombre"
            ></v-text-field>
          </v-flex>
        </v-layout>
        <v-layout row>
           <!--<v-subheader class="grey--text text--lighten-1">Focus</v-subheader>-->
        <v-flex xs1></v-flex>
        <v-flex xs2>
            <v-text-field
              label="Ciudad"
            ></v-text-field>
          </v-flex>
          <v-flex xs2></v-flex>
          <v-flex xs6>
            <!--<v-select v-bind:items="[{ text: 'Mobile' }]" label="Mobile" dark></v-select>-->
            <v-text-field
              label="Direccion"
            ></v-text-field>
          </v-flex>
        </v-layout>
         <v-layout row>
           <!--<v-subheader class="grey--text text--lighten-1">Focus</v-subheader>-->
        <v-flex xs1></v-flex>
        <v-flex xs2>
            <v-text-field
              label="Telefono"
            ></v-text-field>
          </v-flex>
          <v-flex xs2></v-flex>
          <v-flex xs6>
            <!--<v-select v-bind:items="[{ text: 'Mobile' }]" label="Mobile" dark></v-select>-->
            <v-text-field
              label="e-mail"
            ></v-text-field>
          </v-flex>
        </v-layout>
        <v-layout row>
           <!--<v-subheader class="grey--text text--lighten-1">Focus</v-subheader>-->
        <v-flex xs10></v-flex>
          <v-flex xs3>
            <!--<v-select v-bind:items="[{ text: 'Mobile' }]" label="Mobile" dark></v-select>-->
            <v-btn dark fab class="pink" @click.native="Agregar" v-model="abrir">
                <v-icon>save</v-icon>
            </v-btn>
            <v-btn dark fab class="pink" @click.native="Agregar" v-model="abrir">
                <v-icon>cancel</v-icon>
            </v-btn>
          </v-flex>
        </v-layout>
      </v-container>
        </v-card>
        
        <v-flex xs8>
            
            
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
      cedula:null,
      nombre: null,
      apellidos: null,
      direccion:null,
      ciudad: null,
      telefono: null,
      email: null,
      role: null,
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














