<template>
  <v-container fluid grid-list-lg>
    <v-layout row wrap>
      <v-flex xs12 sm12 >
        <v-card>
          <v-toolbar class="cyan" >
            <!--<v-toolbar-side-icon></v-toolbar-side-icon>-->
            <v-icon dark>motorcycle</v-icon>
            <v-toolbar-title class="white--text">Tipo de Moto</v-toolbar-title>
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
                    label="Referencia"
                    class="chirrete-text-field"
                  ></v-text-field>
                </v-flex>
                <v-flex xs12 sm2>
                  <v-select
                    v-bind:items="states"
                    v-model="a1"
                    label="Marca"
                    autocomplete
                  ></v-select>
                </v-flex>
                <v-flex xs12 sm2>
                  <v-text-field
                    label="Cilindraje"
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
                      label="Referencia"
                      class="chirrete-text-field"
                    ></v-text-field>
                  </v-flex>
                  <v-flex xs12 sm3>
                    <v-select
                        v-bind:items="states"
                        v-model="a1"
                        label="Marca"
                        autocomplete
                    ></v-select>
                 </v-flex>
                  <v-flex xs12 sm3>
                    <v-text-field
                      label="Cilindraje"
                      class="chirrete-text-field"
                    ></v-text-field>
                  </v-flex>
                  <v-flex xs12 sm1></v-flex>
                  <v-btn dark fab small class="pink" @click.native="Agregar" v-model="abrir">
                      <v-icon>save</v-icon>
                  </v-btn>
                  <v-btn dark fab small class="pink" @click.native="Cerrar" v-model="abrir">
                      <v-icon>cancel</v-icon>
                  </v-btn>
                </v-layout>
                <!--<v-layout>
                  <v-flex xs12 sm3>
                    <v-text-field
                      label="Eliminar"
                      class="chirrete-text-field"
                    ></v-text-field>
                  </v-flex>
                  <v-flex xs12 sm3>
                    <v-text-field
                      label="Telefono"
                      class="chirrete-text-field"
                    ></v-text-field>
                  </v-flex>
                  <v-flex xs12 sm3>
                    <v-text-field
                      label="e-mail"
                      class="chirrete-text-field"
                    ></v-text-field>
                  </v-flex>
                  <v-flex xs12 sm10></v-flex>
                  <v-btn dark fab small class="pink" @click.native="Cerrar" v-model="abrir">
                      <v-icon>cancel</v-icon>
                  </v-btn>
                </v-layout>-->
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
                <td style="font-weight: bold; width:30%;">{{ props.item.referencia |uppercase}}</td>
                <td class="" style="width:30%;">{{ props.item.marca |uppercase}}</td>
                <td class="text-xs-left" style="width:30%;">{{ props.item.cilindraje |uppercase}}</td>
                <td class="text-xs-right ma-0 pa-0 pl-2">
                  <v-btn dark fab small class="cyan" @click.native="Abrir" v-model="abrir">
                      <v-icon>edit</v-icon>                   
                    </v-btn>
                </td>
                <td class="text-xs-right ma-0 pa-0">
                    <v-btn dark fab small class="green" @click.native="Abrir" v-model="abrir">
                      <v-icon>visibility</v-icon>
                    </v-btn>
                </td>
                <td class="text-xs-right ma-0 pa-0">
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
          marca:null,
          referencia:null,
          cilindraje:null,
          headers: [
          {
            text: 'referencia',
            align: 'left',
            sortable: false,
            value: 'referencia'
          },
          {
            text: 'Marca',
            align: 'left',
            sortable: false,
            value: 'marca'
          },
          {
            text: 'Cilidraje(cc)',
            align: 'left',
            sortable: false,
            value: 'cilindraje'
          },
        ],
        items: [
          {
            marca:"YAMAHA",
            referencia:"RX115",
            cilindraje:"115",
          },
          {
            marca:"YAMAHA",
            referencia:"YW125",
            cilindraje:"125",
          },
          {
            marca:"YAMAHA",
            referencia:"t115 fi",
            cilindraje:"115",
          },
          {
            marca:"YAMAHA",
            referencia:"t110",
            cilindraje:"110",
          },
          {
            marca:"YAMAHA",
            referencia:"libero 125",
            cilindraje:"115",
          },
          {
            marca:"YAMAHA",
            referencia:"RX115",
            cilindraje:"115",
          },
          {
            marca:"honda",
            referencia:"wave",
            cilindraje:"100",
          },
          {
            marca:"YAMAHA",
            referencia:"wave 2",
            cilindraje:"125",
          },
          {
            marca:"suzuki",
            referencia:"best",
            cilindraje:"125",
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
