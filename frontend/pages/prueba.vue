<template>
  <v-container fluid grid-list-lg>
    <v-layout row wrap>
      <v-flex xs12 sm12 >
        <v-card >
          <v-toolbar class="red drken-1" >
            <!--<v-toolbar-side-icon></v-toolbar-side-icon>-->
            <v-icon dark>motorcycle</v-icon>
            <v-toolbar-title class="white--text">Prueba</v-toolbar-title>
            <v-fab-transition>
              <v-btn
                class="grey darken-2"
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
          					label="Cedula"
          					class="chirrete-text-field"
          				></v-text-field>
          			</v-flex>
          			<v-flex xs12 sm4>
          				<v-text-field
          					label="Nombre"
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
          	<v-layout v-if="abrir" class="pa-3 ">
          		<v-card-text class="pb-0 pt-0 elevation-2" >
            		<v-layout>
          				<v-flex xs12 sm3>
          					<v-text-field
          						label="Cedula"
          						class="chirrete-text-field"
          					></v-text-field>
          				</v-flex>
          				<v-flex xs12 sm3>
          					<v-text-field
          						label="Nombre"
          						class="chirrete-text-field"
          					></v-text-field>
          				</v-flex>
          				<v-flex xs12 sm3>
          					<v-text-field
          						label="Direccion"
          						class="chirrete-text-field"
          					></v-text-field>
          				</v-flex>
          				<v-flex xs12 sm1></v-flex>
          				<!--<v-btn dark fab small class="grey darken-2" @click.native="Agregar" v-model="abrir">
                			<v-icon>save</v-icon>
            			</v-btn>-->
            		</v-layout>
          			<v-layout>
          				<v-flex xs12 sm3>
          					<v-text-field
          						label="Ciudad"
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
          				<v-flex xs12 sm1></v-flex>
          				<!--<v-btn dark fab small class="grey darken-2" @click.native="Cerrar" v-model="abrir">
                			<v-icon>cancel</v-icon>
            			</v-btn>-->
                  <v-speed-dial
                    v-model="fab"
                    :bottom="true"
                    :right="true"
                    :direction="left"
                    :hover="true"
                    :transition="'slide-y-reverse-transition'"
                  >
                    <v-btn
                      slot="activator"
                      class="blue darken-2"
                      dark
                      fab
                      hover
                      v-model="fab"
                    >
                      <v-icon>account_circle</v-icon>
                      <v-icon>close</v-icon>
                    </v-btn>
                    <v-btn
                      fab
                      dark
                      small
                      class="green"
                      @click.native="Cerrar"
                    >
                      <v-icon>save</v-icon>
                    </v-btn>
                    <v-btn
                      fab
                      dark
                      small
                      class="indigo"
                    >
                      <v-icon>cancel</v-icon>
                    </v-btn>
                </v-speed-dial>
          		</v-layout>
          		<v-spacer></v-spacer>
          	 </v-card-text>
          </v-layout>
          	<v-layout class="pa-3">
          		<v-data-table
        			v-bind:headers="headers"
        			:items="items"
        			hide-actions
        			class="elevation-5 caption"
       				v-bind:search="search"
				    >
   					  
              <template slot="headers" scope="props">
                <tr>
                  <th class="text-xs-center"v-for="header in props.headers" :key="header">{{ header.text }}</th>
                </tr>
              </template>

              <template slot="items" scope="props">
       				  <td class="text-xs-center" style="font-weight: bold; width:15%;">{{ props.item.cedula }}</td>
       					<td class="text-xs-center" style="width:45%;">{{ props.item.nombre}}</td>
       					<td class="text-xs-center" style="width:15%;">{{ props.item.telefono}}</td>
       					<td class="text-xs-center" style="width:15%;">{{ props.item.direccion}}</td>
       					<td class="text-xs-right ma-0 pa-0 pl-2" style="width:5px">
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
      direction: "top",
      fab: false,
      fling: false,
      hover: false,
      tabs: null,
      top: false,
      right: true,
      bottom: true,
      left: false,
      transition: 'slide-y-reverse-transition',
          


          abrir:false,
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
            nombre:"Jose del Carmen aristizabal zabaleta",
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
        console.log(this.abrir)
      },
      Cerrar(){
        this.abrir=false
        console.log(this.abrir)
      },
    },
    
    watch: {
      top (val) {
        this.bottom = !val
      },
      right (val) {
        this.left = !val
      },
      bottom (val) {
        this.top = !val
      },
      left (val) {
        this.right = !val
      }
    },
     
     computed: {
      activeFab () {
        switch (this.tabs) {
          case 'one': return { 'class': 'purple', icon: 'account_circle' }
          case 'two': return { 'class': 'red', icon: 'edit' }
          case 'three': return { 'class': 'green', icon: 'keyboard_arrow_up' }
          default: return {}
        }
      }
    }
  }
</script>

<style>
  /* This is for documentation purposes and will not be needed in your application */
  #create .speed-dial {
    position: absolute;
  }

  #create .btn--floating {
    position: relative;
  }
</style>
