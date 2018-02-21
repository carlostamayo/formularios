<template>
  <div>
  
  <v-card>
    <v-layout>
      <v-btn dark fab class="pink" @click.native="Abrir" v-model="abrir">
        <v-icon>add</v-icon>
      </v-btn>
      <v-flex x12 sm1></v-flex>
      <v-flex xs12 sm1>
        <v-text-field
            class="chirrete-text-field"
            label="Cedula"
            v-model="cedula"
        ></v-text-field>
      </v-flex xs12 sm1>
      <v-flex xs12 sm1></v-flex>
      <v-flex xs12 sm3>
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
  </v-card>
    <br><br>
        <v-layout row wrap v-if="abrir">
          <v-flex xs12>
            <v-card>
              <!--<v-toolbar class="indigo" dark>
                <v-toolbar-title>Datos de usuario</v-toolbar-title>
              </v-toolbar>-->
              <v-container fluid>
                <v-layout row>
                  <v-flex xs1></v-flex>
                  <v-flex xs2>
                    <v-text-field
                        label="Cedula"
                    ></v-text-field>
                  </v-flex>
                  <v-flex xs2></v-flex>
                  <v-flex xs6>
                    <v-text-field
                        label="Nombre"
                    ></v-text-field>
                  </v-flex>
                </v-layout>
                <v-layout row>
                  <v-flex xs1></v-flex>
                  <v-flex xs2>
                    <v-text-field
                         label="Ciudad"
                    ></v-text-field>
                  </v-flex>
                  <v-flex xs2></v-flex>
          <v-flex xs6>
            <v-text-field
                label="Direccion"
            ></v-text-field>
          </v-flex>
        </v-layout>
        <v-layout row>
          <v-flex xs1></v-flex>
          <v-flex xs2>
            <v-text-field
                label="Telefono"
            ></v-text-field>
          </v-flex>
          <v-flex xs2></v-flex>
          <v-flex xs6>
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
            <v-btn dark fab small class="pink" @click.native="Cerrar" v-model="abrir">
                <v-icon>save</v-icon>
            </v-btn>
            <v-btn dark fab small class="pink" @click.native="Cerrar" v-model="abrir">
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
  
  <br><br>
    <v-data-table
        v-bind:headers="headers"
        :items="items"
        hide-actions
        class="elevation-1 caption"
        v-bind:search="search"
    >
      <template slot="items" scope="props">
        <td style="font-weight: bold;">{{ props.item.cedula }}</td>
        <td class="caption">{{ props.item.nombre}}</td>
        <td class="text-xs-left caption">{{ props.item.telefono}}</td>
        <td class="text-xs-left">{{ props.item.direccion}}</td>
        <td class="text-xs-right" style="width:5px">
          <v-btn dark fab small class="cyan" @click.native="Cerrar" v-model="abrir">
            <v-icon>edit</v-icon>
          </v-btn>
        </td>
        <td class="text-xs-right">
          <v-btn dark fab small class="green" @click.native="Cerrar" v-model="abrir">
            <v-icon>visibility</v-icon>
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
          abrir:false,
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
      Abrir(){
        this.abrir=true
        console.log(this.cedula)
      },
      Cerrar(){
        this.abrir=false
        console.log(this.cedula)
      },
    }
  }
</script>
<style>
  .chirrete-text-field input{
    font-size: 14px;
  }
</style>