<template>
  <div>
   <v-layout wrap class="grey lighten-4">
    <v-btn dark fab class="pink" @click.native="Agregar" v-model="abrir">
      <v-icon>add</v-icon>
    </v-btn>
    <v-flex x12 sm1></v-flex>
    <v-flex xs12 sm2>
      <v-text-field
          label="Orden"
          v-model="orden"
          v-on:keyup="Agregar"
      ></v-text-field>
      </v-flex xs12 sm1>
    <v-flex xs12 sm1></v-flex>
    <v-flex xs12 sm4>
      <v-text-field
         label="Nombre"
         v-model="nombre"
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
        <td style="font-weight: bold;">{{ props.item.orden }}</td>
        <td >{{ props.item.nombre}}</td>
        <td class="text-xs-left">{{ props.item.placa}}</td>
        <td class="text-xs-left">{{ props.item.fecha}}</td>
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
          orden:null,
          nombre:null,
          placa:null,
          fecha:null,
          headers: [
          {
            text: '# Orden',
            align: 'left',
            sortable: false,
            value: 'orden'
          },
          {
            text: 'Nombre',
            align: 'left',
            sortable: false,
            value: 'nombre'
          },
          {
            text: 'Placa',
            align: 'left',
            sortable: false,
            value: 'placa'
          },
          {
            text: 'Fecha',
            align: 'left',
            sortable: false,
            value: 'fecha'
          },
        ],
        items: [
          {
            orden:"001",
            nombre:"Jose del Carmen aristizabal zabaleta fernandez de la peña",
            placa:"MHK25D",
            fecha:"19-02-18",
          },
          {
            orden:"002",
            nombre:"Jose del Carmen aristizabal zabaleta fernandez de la peña",
            placa:"MHK25D",
            fecha:"19-02-18",
          },
          {
            orden:"003",
            nombre:"Jose del Carmen aristizabal zabaleta fernandez de la peña",
            placa:"MHK25D",
            fecha:"19-02-18",
          },
          {
            orden:"004",
            nombre:"Jose del Carmen aristizabal zabaleta fernandez de la peña",
            placa:"MHK25D",
            fecha:"19-02-18",
          },
          {
           orden:"005",
            nombre:"Jose del Carmen aristizabal zabaleta fernandez de la peña",
            placa:"MHK25D",
            fecha:"19-02-18",
          },
          {
            orden:"006",
            nombre:"Jose del Carmen aristizabal zabaleta fernandez de la peña",
            placa:"MHK25D",
            fecha:"19-02-18",
          },
          {
            orden:"007",
            nombre:"Jose del Carmen aristizabal zabaleta fernandez de la peña",
            placa:"MHK25D",
            fecha:"19-02-18",
          },
          {
            orden:"008",
            nombre:"Jose del Carmen aristizabal zabaleta fernandez de la peña",
            placa:"MHK25D",
            fecha:"19-02-18",
          },
          {
            orden:"009",
            nombre:"Jose del Carmen aristizabal zabaleta fernandez de la peña",
            placa:"MHK25D",
            fecha:"19-02-18",
          },
          {
            orden:"010",
            nombre:"Jose del Carmen aristizabal zabaleta fernandez de la peña",
            placa:"MHK25D",
            fecha:"19-02-18",
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