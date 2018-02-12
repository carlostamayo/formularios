<template>
  <v-container fluid >
    <v-layout row wrap>
      <v-flex xs12 md6 offset-md3 >
        <v-card>
          <v-toolbar color="red" dark>
            <v-toolbar-title>Tipo Motocicleta</v-toolbar-title>
          </v-toolbar>
          <v-card-text>
            <span class="title">Información personal</span>
            <v-select
             label="Marca"
             v-model="a1"
            :items="items"
            v-bind:items="states"
            :error-messages="selectErrors"
            @change="$v.select.$touch()"
            @blur="$v.select.$touch()"
            required autocomplete
            ></v-select>
            <v-text-field
              label="Referencia"
              v-model="referencia"
              required
            ></v-text-field>
            <v-text-field
              label="Cilindraje"
              v-model="cilindraje"
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
      marca:null,
      referencia:null,
      cilindraje:null,
      a1: null,
        states: [
          'Alabama','Alaska','American Samoa','Arizona',
          'Arkansas','California','Colorado','Connecticut',
          'Delaware','District of Columbia','Federated States of Micronesia',
          'Florida','Georgia','Guam','Hawaii','Idaho',
          'Illinois','Indiana','Iowa','Kansas','Kentucky',
          'Louisiana','Maine','Marshall Islands','Maryland',
          'Massachusetts','Michigan','Minnesota','Mississippi',
          'Missouri','Montana','Nebraska','Nevada',
          'New Hampshire','New Jersey','New Mexico','New York',
          'North Carolina','North Dakota','Northern Mariana Islands','Ohio',
          'Oklahoma','Oregon','Palau','Pennsylvania','Puerto Rico',
          'Rhode Island','South Carolina','South Dakota','Tennessee',
          'Texas','Utah','Vermont','Virgin Island','Virginia',
          'Washington','West Virginia','Wisconsin','Wyoming'
        ],
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

