<template>
  <div>
   <v-layout wrap class="grey lighten-4">
    <v-btn dark fab class="pink" @click.native="Agregar" v-model="abrir">
      <v-icon>add</v-icon>
    </v-btn>
    <v-flex x12 sm1></v-flex>
    <v-flex xs12 sm2>
      <v-text-field
          label="Cedula"
          v-model="cedula"
          v-on:keyup="Agregar"
      ></v-text-field>
      </v-flex xs12 sm1>
    <v-flex xs12 sm1></v-flex>
    <v-flex xs12 sm4>
      <v-text-field
         label="Nombre"
         v-model="search"
      ></v-text-field>
      </v-flex>
      <v-spacer></v-spacer>
      <v-btn icon>
        <v-icon>search</v-icon>
      </v-btn>
    </v-layout>
    <br><br>
    <v-data-table
        v-bind:headers="headers"
        :items="items"
        hide-actions
        class="elevation-1"
        v-bind:search="search"
    >
      <template slot="items" scope="props">
        <td style="font-weight: bold;">{{ props.item.cedula }}</td>
        <td >{{ props.item.nombre}}</td>
        <td class="text-xs-left">{{ props.item.telefono}}</td>
        <td class="text-xs-left">{{ props.item.direccion}}</td>
        <td class="text-xs-right">
          <v-btn dark fab small class="cyan" @click.native="Agregar" v-model="abrir">
            <v-icon>edit</v-icon>
          </v-btn>
        </td>
        <td class="text-xs-right">
          <v-btn dark fab small class="grey" @click.native="Agregar" v-model="abrir">
            <v-icon>delete</v-icon>
          </v-btn>
        </td>
      </template>
   </v-data-table>
  </div>
</template>



<script>
  export default {
    data () {
      return {
          cedula:null,
          nombre:null,
          headers: [
          {
            text: 'Cedula',
            align: 'left',
            sortable: false,
            value: 'cedula'
          },
          {
            text: 'Nombre',
            align: 'left',
            sortable: false,
            value: 'nombre'
          },
          {
            text: 'Direccion',
            align: 'left',
            sortable: false,
            value: 'telefono'
          },
          {
            text: 'Telefono',
            align: 'left',
            sortable: false,
            value: 'direccion'
          },
        ],
        items: [
          {
            cedula:"1065864163",
            nombre:"Jose del Carmen aristizabal zabaleta fernandez de la peña",
            telefono:"3136817175",
            direccion:"Calle 12 # 26-46",
          },
          {
            cedula:"1065864163",
            nombre:"Carlos  Andres Tamayo Benjumea",
            telefono:"3136817175",
            direccion:"Calle 12 # 26-46",
          },
          {
            cedula:"1065864163",
            nombre:"Carlos  Andres Tamayo Benjumea",
            telefono:"3136817175",
            direccion:"Calle 12 # 26-46",
          },
          {
            cedula:"1065864163",
            nombre:"Carlos  Andres Tamayo Benjumea",
            telefono:"3136817175",
            direccion:"Calle 12 # 26-46",
          },
          {
            cedula:"1065864163",
            nombre:"Carlos  Andres Tamayo Benjumea",
            telefono:"3136817175",
            direccion:"Calle 12 # 26-46",
          },
          {
            cedula:"1065864163",
            nombre:"Carlos  Andres Tamayo Benjumea",
            telefono:"3136817175",
            direccion:"Calle 12 # 26-46",
          },
          {
            cedula:"1065864163",
            nombre:"Carlos  Andres Tamayo Benjumea",
            telefono:"3136817175",
            direccion:"Calle 12 # 26-46",
          },
          {
            cedula:"1065864163",
            nombre:"Jose del Carmen aristizabal zabaleta fernandez de la peña",
            telefono:"3136817175",
            direccion:"Calle 12 # 26-46",
          },
          {
            cedula:"1065864163",
            nombre:"Carlos  Andres Tamayo Benjumea",
            telefono:"3136817175",
            direccion:"Calle 12 # 26-46",
          },
          {
            cedula:"1065864163",
            nombre:"Carlos  Andres Tamayo Benjumea",
            telefono:"3136817175",
            direccion:"Calle 12 # 26-46",
          },
          {
            cedula:"1065864163",
            nombre:"Carlos  Andres Tamayo Benjumea",
            telefono:"3136817175",
            direccion:"Calle 12 # 26-46",
          },
          {
            cedula:"1065864163",
            nombre:"Carlos  Andres Tamayo Benjumea",
            telefono:"3136817175",
            direccion:"Calle 12 # 26-46",
          },
          {
            cedula:"1065864163",
            nombre:"Carlos  Andres Tamayo Benjumea",
            telefono:"3136817175",
            direccion:"Calle 12 # 26-46",
          },
          {
            cedula:"1065864163",
            nombre:"Carlos  Andres Tamayo Benjumea",
            telefono:"3136817175",
            direccion:"Calle 12 # 26-46",
          },
        ] 
      }
    },
    methods:{
      Agregar(){
        this.abrir=true
        console.log(this.cedula)
      }
    }
  }
</script>