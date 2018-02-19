<template>
  <v-form v-model="valid">
    <!--Datos Cliente-->
    <v-layout wrap>
       <v-flex xs12 sm1></v-flex>
      <!--<h6>Datos Cliente</h6>-->
    </v-layout>
    <v-layout wrap>
      <v-flex xs12 sm1></v-flex>
      <v-flex xs12 sm2>
        <v-select
          v-bind:items="clientes"
          v-model="cedula"
          label="Cedula"
          maxlength="10"
          autocomplete
      ></v-select>
      </v-flex xs12 sm1>
      <v-btn icon class="black--text"  @click.native="limpiarCliente">
          <v-icon>delete</v-icon>
      </v-btn>
      <v-btn icon class="black--text" @click.native="guardar">
          <v-icon>add</v-icon>
      </v-btn>
      <v-flex xs12 sm1></v-flex>
      <v-flex xs12 sm6>
        <v-text-field
          v-model="nombre"
          label="Nombre"
          readonly
      ></v-text-field>
      </v-flex>
    </v-layout>
    <v-layout wrap>
      <v-flex xs12 sm1></v-flex>
      <v-flex xs12 sm2>
        <v-text-field
          v-model="telefono"
          label="Telefono"
          readonly
      ></v-text-field>
      </v-flex xs12 sm1>
      <v-btn icon class="black--text">
        <v-icon>delete</v-icon>
      </v-btn>
      <v-btn icon class="black--text">
        <v-icon>add</v-icon>
      </v-btn>
      <v-flex xs12 sm1></v-flex>
      <v-flex xs12 sm6>
        <v-text-field
          readonly
          v-model="direccion"
          label="Direccion"
      ></v-text-field>
      </v-flex>
    </v-layout>
    
    <v-divider></v-divider>
    
    <!--Datos Motocicleta-->
    <v-layout>
       <v-flex xs12 sm1></v-flex>
    </v-layout>
    <v-layout wrap>
      <v-flex xs12 sm1></v-flex>
      <v-flex xs12 sm2>
        <v-select
          v-bind:items="placas"
          v-model="placa"
          label="Placa"
          maxlength="10"
          autocomplete
      ></v-select>
      </v-flex>
      <v-flex xs12 sm2>
        <v-btn icon class="black--text"  @click.native="limpiarMoto">
          <v-icon>delete</v-icon>
        </v-btn>
        <v-btn icon class="black--text">
          <v-icon>add</v-icon>
        </v-btn>
      </v-flex>
  </v-layout>
  <v-layout wrap>
      <v-flex xs12 sm1></v-flex>
      <v-flex xs12 sm2>
        <v-text-field
          readonly
          v-model="referencia"
          label="Referencia"
      ></v-text-field>
      </v-flex>
      <v-flex xs12 sm1></v-flex>
      <v-flex xs12 sm2>
        <v-text-field
          readonly
          v-model="color"
          label="Color"
      ></v-text-field>
      </v-flex>
      <v-flex xs12 sm1></v-flex>
      <v-flex xs12 sm2>
        <v-text-field
         v-model="km"
          label="Kilometraje"
          maxlength="5"
          suffix="Kms"
      ></v-text-field>
      </v-flex>
    </v-layout>  

<v-divider></v-divider>
    
    <!--Datos Tecnico-->
    <v-layout>
       <v-flex xs12 sm1></v-flex>
    </v-layout>
    <v-layout wrap>
      <v-flex xs12 sm1></v-flex>
      <v-flex xs12 sm2>
        <v-select
          v-bind:items="tecnicos"
          v-model="tecnico"
          label="Tecnico"
          maxlength="30"
          autocomplete
      ></v-select>
      </v-flex>
      <v-flex xs12 sm2>
        <v-btn icon class="black--text"  @click.native="">
          <v-icon>delete</v-icon>
        </v-btn>
        <v-btn icon class="black--text">
          <v-icon>add</v-icon>
        </v-btn>
      </v-flex>
  </v-layout>

  <v-divider></v-divider>

  <v-layout row wrap>
   <v-flex xs12 sm1></v-flex>
   <v-flex xs12 sm3>
    <v-dialog
      persistent
      v-model="modal"
      lazy
      full-width
    >
    <v-text-field
      slot="activator"
      label="Fecha Salida"
      v-model="e3"
      prepend-icon="event"
      readonly
    ></v-text-field>
    <v-date-picker v-model="e3" scrollable >
      <template scope="{ save, cancel }">
        <v-card-actions>
          <v-btn flat primary @click.native="cancel()">Cancel</v-btn>
          <v-btn flat primary @click.native="save()">Save</v-btn>
        </v-card-actions>
      </template>
    </v-date-picker>
    </v-dialog>
  </v-flex>
  
  <v-flex xs12 sm1></v-flex>
   <v-flex xs12 sm3>
      <v-dialog
        persistent
        v-model="modal2"
        lazy
      >
        <v-text-field
          slot="activator"
          label="Hora Salida"
          v-model="e6"
          prepend-icon="access_time"
          readonly
        ></v-text-field>
        <v-time-picker v-model="e6" actions>
          <template scope="{ save, cancel }">
            <v-card-actions>
              <v-btn flat primary @click.native="cancel()">Cancel</v-btn>
              <v-btn flat primary @click.native="save()">Save</v-btn>
            </v-card-actions>
          </template>
        </v-time-picker>
      </v-dialog>
    </v-flex>
   </v-layout>
   <v-divider></v-divider>
  </v-form>
 </template>

<script>
  export default {
    data () {
      return {
        e3: null,
        menu: false,
        modal: false,


        e6: null,  //reloj
        modal2: false,
        e7: null,  //reloj 2
        modal3: false,
        
        cedula: null,
        nombre: null,
        telefono: null,
        direccion: null,
        
        placa: null,
        referencia:null,
        color: null,
        km: null,
        tecnico: null,

        clientes: ['1065864163','1098','19872'],
        placas: [
          'MHK25D','RJO45A','XUY20D','MHE45E'],  
        valid: false,
        name: '',
        nameRules: [
          (v) => !!v || 'Name is required',
          (v) => v.length <= 10 || 'Name must be less than 10 characters'
        ],
      }
    },
    
    methods: {
      limpiarCliente(){
        this.cedula=""
        this.nombre=""
        this.telefono=""
        this.direccion=""
      },
      limpiarMoto(){
        this.placa=""
        this.referencia=""
        this.color=""
        this.km=""
        this.tecnico=""
      },
      guardar(){
        this.nombre="Carlos Andres Tamayo"
        this.telefono="  3136817175"
        this.direccion="calle 12 # 26-46"
        this.placa="OJE71E"
        this.referencia="T115 FI"
        this.color="Negro"
        this.km="23400"
      }
    },
  }
</script>