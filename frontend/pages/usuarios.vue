<template>
  <v-container fluid>
    <v-layout row wrap>
      <v-flex xs12 md6 offset-md3>
        <v-card>
          <v-toolbar color="red" dark>
            <v-toolbar-title>Datos de usuario</v-toolbar-title>
          </v-toolbar>
          <v-card-text>
            <span class="title">Información personal</span>
            <v-text-field
              label="Cédula"
              class="mt-5"
              v-model="cedula"
              required
            ></v-text-field>
            <v-text-field
              label="Nombre"
              v-model="nombre"
              required
            ></v-text-field>
            <v-text-field
              label="Apellidos"
              v-model="apellidos"
              required
            ></v-text-field>
            <v-text-field
              label="Dirección"
              v-model="direccion"
              required
            ></v-text-field>
            <v-text-field
              label="Ciudad"
              v-model="ciudad"
              required
            ></v-text-field>
            <v-text-field
              label="Telefono"
              v-model="telefono"
              required
            ></v-text-field>
            <v-text-field
              label="Email"
              v-model="email"
            ></v-text-field>
            <v-select
             label="Rol"
             v-model="role"
            :items="items"
            :error-messages="selectErrors"
            @change="$v.select.$touch()"
            @blur="$v.select.$touch()"
            required
            ></v-select>
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

