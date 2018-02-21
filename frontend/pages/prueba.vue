<template>
  <v-container fluid grid-list-lg>
    <v-layout row wrap>
      <v-flex xs12 sm12 >
        <v-card >
          <v-toolbar class="red accent-4" >
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
          				<v-btn dark fab small class="grey darken-2" @click.native="Agregar" v-model="abrir">
                			<v-icon>save</v-icon>
            			</v-btn>
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
          				<v-btn dark fab small class="grey darken-2" @click.native="Cerrar" v-model="abrir">
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
        			class="elevation-5 caption"
       				v-bind:search="search"
				>
   					  <template slot="items" scope="props">
       				    <td style="font-weight: bold;">{{ props.item.cedula }}</td>
       					<td class="caption">{{ props.item.nombre}}</td>
       					<td class="text-xs-left caption">{{ props.item.telefono}}</td>
       					<td class="text-xs-left">{{ props.item.direccion}}</td>
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
