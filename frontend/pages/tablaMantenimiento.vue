<template>
  <v-container fluid grid-list-lg>
    <v-layout row wrap>
      <v-flex xs12 sm12 >
        <v-card>
          <v-toolbar class="cyan" >
            <!--<v-toolbar-side-icon></v-toolbar-side-icon>-->
            <v-icon dark>motorcycle</v-icon>
            <v-toolbar-title class="white--text">Tabla Mantenimiento</v-toolbar-title>
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
                <v-flex xs12 sm3>
                  <v-select
                        v-bind:items="states"
                        v-model="a1"
                        label="Referencia"
                        autocomplete
                        class="chirrete-text-field"
                    ></v-select>
                </v-flex>
                <v-flex xs12 sm2></v-flex>
                <v-spacer></v-spacer>
                <v-flex xs12 sm2 class="pa-3">
                  <v-btn dark fab small class="pink" @click.native="Abrir" v-model="abrir">
                      <v-icon>edit</v-icon>
                  </v-btn>
                  <v-btn dark fab small class="pink" @click.native="Abrir" v-model="abrir">
                      <v-icon>visibility</v-icon>
                  </v-btn>
                </v-flex>
                <!--<v-flex xs12 sm2>
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
                </v-flex>-->
                
                  <!--<v-spacer></v-spacer>
                  <v-btn fab large icon>
                    <v-icon>search</v-icon>
                  </v-btn>-->
                
              </v-layout>
            </v-card-text>
            </v-layout>
            <v-layout v-if="abrir" class="pa-3">
              <v-card-text class="gray pb-0 pt-0 elevation-2" >
                <v-layout>
                  <v-flex xs12 sm3>
                    <v-select
                        v-bind:items="states"
                        v-model="a1"
                        label="Referencia"
                        autocomplete
                        class="chirrete-text-field"
                    ></v-select>
                  </v-flex>
                  <!--<v-flex xs12 sm3>
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
                  </v-flex>-->
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
                <td class="" style="font-weight: bold;">{{ props.item.servicio|uppercase}}</td>
                <td class="text-xs-center">
                    <input type="text" maxlength="5" style="width:40px;" value=""></input>
                </td>
                <td class="text-xs-center">
                    <input type="text" maxlength="2" style="width:20px;" value="NA"></input>
                </td>
                <td><v-checkbox label=""  
                        v-model="props.item.aplica"
                        value="" 
                        hide-details></v-checkbox></td>
                <!--<td class="text-xs-right" style="width:5px">
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
                </td>-->
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
          ex4:false,
          abrir:false,
          marca:null,
          referencia:null,
          cilindraje:null,
          headers: [
          {
            text: 'Servicio Taller',
            align: 'left',
            sortable: false,
            value: 'servicio'
          },
          {
            text: 'Kilometros',
            align: 'center',
            sortable: false,
            value: 'km'
          },
          {
            text: 'Tiempo',
            align: 'center',
            sortable: false,
            value: 'tiempo'
          },
          {
            text: 'Aplica',
            align: 'center',
            sortable: false,
            value: 'aplica'
          },
        ],
        items: [
          {
            servicio:"cambio de aceite",
            km:"2000",
            tiempo:"NA",
            aplica:true,
          },
          {
            servicio:"cambio valvulina",
            km:"4000",
            tiempo:"NA",
            aplica:true,
          },
          {
            servicio:"cambio bujia",
            km:"6000",
            tiempo:"NA",
            aplica:true,
          },
          {
            servicio:"cambio filtro de aceite",
            km:"4000",
            tiempo:"NA",
            aplica:true,
          },
          {
            servicio:"cambio de liquido frenos",
            km:"20000",
            tiempo:"24",
            aplica:true,
          },
        ],
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
