<template>
  <v-container fluid grid-list-lg>
    <v-layout row wrap>
      <v-flex xs12 sm12 >
        <v-card>
          <v-toolbar class="cyan" >
            <!--<v-toolbar-side-icon></v-toolbar-side-icon>-->
            <v-toolbar-title class="white--text">Motocicleta</v-toolbar-title>
            <v-fab-transition>
              <v-btn
                class="indigo"
                fab
                dark
                small
                absolute
                bottom
                right
                v-show="!hidden"
                 @click.native="Abrir"
              >
                <v-icon>add</v-icon>
              </v-btn>
            </v-fab-transition>
          </v-toolbar>
          </v-card-text>
            
          <v-layout class="pa-3 pt-4">
            <v-card-text class="gray pb-0 pt-0 elevation-2">
              <v-layout>
                <v-flex xs12 sm2>
                  <v-text-field
                    label="Placa"
                    class="chirrete-text-field"
                  ></v-text-field>
                </v-flex>
                <v-flex xs12 sm4>
                  <v-text-field
                    label="Propietario"
                    class="chirrete-text-field"
                  ></v-text-field>
                </v-flex>
                <v-spacer></v-spacer>
                <v-btn fab large icon>
                  <v-icon>search</v-icon>
                </v-btn>
              </v-layout>
            </v-card-text>
          </v-layout>
          
          <v-layout v-if="abrir" class="pa-3">
            <v-card-text class="gray pb-0 pt-0 elevation-2" >
                <v-layout>
                  <v-flex xs12 sm3>
                    <v-text-field
                      label="Placa"
                      class="chirrete-text-field"
                    ></v-text-field>
                  </v-flex>
                  <v-flex xs12 sm3>
                    <v-text-field
                      label="Referencia"
                      class="chirrete-text-field"
                    ></v-text-field>
                  </v-flex>
                  <v-flex xs12 sm3>
                    <v-text-field
                      label="Marca"
                      class="chirrete-text-field"
                    ></v-text-field>
                  </v-flex>
                  <v-flex xs12 sm1></v-flex>
                  <v-btn dark fab small class="pink" @click.native="Agregar" v-model="abrir">
                      <v-icon>save</v-icon>
                  </v-btn>
                </v-layout>
                <v-layout>
                  <v-flex xs12 sm3>
                    <v-text-field
                      label="Color"
                      class="chirrete-text-field"
                    ></v-text-field>
                  </v-flex>
                  <v-flex xs12 sm3>
                    <v-text-field
                      label="Propietario"
                      class="chirrete-text-field"
                    ></v-text-field>
                  </v-flex>
                  <v-flex xs12 sm3>
                    <v-text-field
                      label="Km"
                      class="chirrete-text-field"
                    ></v-text-field>
                  </v-flex>
                  <v-flex xs12 sm1></v-flex>
                  <v-btn dark fab small class="pink" @click.native="Cerrar" v-model="abrir">
                      <v-icon>cancel</v-icon>
                  </v-btn>
                </v-layout>
                <v-spacer></v-spacer>
              </v-card-text>
            </v-layout>
            <v-layout class="pa-3">
              <v-data-table
              v-bind:headers="headers"
              :items="items"
              hide-actions
              class="elevation-1 caption"
              v-bind:search="search"
        >
              <template slot="items" scope="props">
                  <td style="font-weight: bold;">{{ props.item.placa | uppercase}}</td>
                <td class="caption">{{ props.item.referencia |uppercase}}</td>
                <td class="text-xs-left caption">{{ props.item.propietario}}</td>
                <td class="text-xs-left">{{ props.item.color | uppercase}}</td>
                <td class="text-xs-right" style="width:5px">
                  <v-btn dark fab small class="cyan" @click.native="Abrir" v-model="abrir">
                      <v-icon>edit</v-icon>                   
                    </v-btn>
                </td>
                <td class="text-xs-right">
                    <v-btn dark fab small class="green" @click.native="Abrir" v-model="abrir">
                      <v-icon>visibility</v-icon>
                    </v-btn>
                </td>
                <td class="text-xs-right">
                    <v-btn dark fab small class="grey" @click.native="Eliminar" v-model="abrir">
                      <v-icon>delete</v-icon>
                   </v-btn>
                </td>
              </template>
          </v-data-table> 
        </v-layout> 
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>
<script>
  export default {
    data () {
      return {
          abrir:false,
          placa:null,
          nombre:null,
          propietario:null,
          color:null,
          headers: [
          {
            text: 'Placa',
            align: 'left',
            sortable: false,
            value: 'cedula'
          },
          {
            text: 'Referencia',
            align: 'left',
            sortable: false,
            value: 'nombre'
          },
          {
            text: 'Propietario',
            align: 'left',
            sortable: false,
            value: 'telefono'
          },
          {
            text: 'Color',
            align: 'left',
            sortable: false,
            value: 'color',
          },
        ],
        items: [
          {
            placa:"MHK25D",
            referencia:"vivar-125",
            propietario:"Carlos andres Tamayo Benjumea",
            color:"negro",
          },
          {
            placa:"xuy20d",
            referencia:"t115 fi",
            propietario:"Joiner Eliecer Sanchez",
            color:"negro",
          },
          {
            placa:"kzf67a",
            referencia:"rx115",
            propietario:"Jose Caceres",
            color:"negro",
          },
        ] 
      }
    },
    methods:{
      Abrir(){
        this.abrir=true
        console.log(this.abrir)
      },
      Cerrar(){
        this.abrir=false
        console.log(this.abrir)
      },
    }
  }
</script>

<style scoped>
  .chirrete-text-field input{
    font-size: 10px;
    width: 10px;
  }
</style>
