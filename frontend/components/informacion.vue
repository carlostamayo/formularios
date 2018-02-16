<template>
  <v-form v-model="valid">
    <v-layout wrap>
      <v-flex xs12 sm1>
          <v-subheader v-text="'Cedula'"></v-subheader>
      </v-flex>
      <v-flex xs12 sm2>
        <v-select
          v-bind:items="clientes"
          v-model="cedula"
          label=""
          id ="textCedula"
          autocomplete
      ></v-select>
      </v-flex xs 1>
      <v-btn icon class="black--text"  @click.native="limpiarCliente">
              <v-icon>delete</v-icon>
            </v-btn>
            <v-btn icon class="black--text" @click.native="guardar">
              <v-icon>add</v-icon>
      </v-btn>
      <v-flex xs1>
        <v-subheader>Nombre</v-subheader>
      </v-flex>
      <v-flex xs6>
        <v-text-field
          name="input-1"
          disabled
          v-model="nombre"
      ></v-text-field>
      </v-flex>
    </v-layout>
    <v-layout row>
      
      <v-flex xs1>
        <v-subheader>Telefono</v-subheader>
      </v-flex>
      <v-flex xs2>
        <v-text-field
          disabled
          v-model="telefono"
      ></v-text-field>
      </v-flex>
      <v-flex xs2></v-flex>
      <v-flex xs1>
        <v-subheader>Direccion</v-subheader>
      </v-flex>
      <v-flex xs5>
        <v-text-field
          disabled
          v-model="direccion"
      ></v-text-field>
      </v-flex>
    </v-layout>
    
    <v-divider></v-divider>
    
    <v-layout wrap>
      <v-flex xs12 sm1>
          <v-subheader v-text="'Placa'"></v-subheader>
      </v-flex>
      <v-flex xs12 sm2>
        <v-select
          v-bind:items="placas"
          v-model="placa"
          label=""
          autocomplete
      ></v-select>
      </v-flex>
      <v-btn icon class="black--text"  @click.native="limpiarMoto">
              <v-icon>delete</v-icon>
            </v-btn>
            <v-btn icon class="black--text">
              <v-icon>add</v-icon>
            </v-btn>
    </v-layout>
    
    <v-layout row>
      <v-flex xs1>
        <v-subheader>Refer</v-subheader>
      </v-flex>
      <v-flex xs2>
        <v-text-field
          name="input-1"
          disabled
          id="testing"
      ></v-text-field>
      </v-flex>
      <v-flex xs1>
        <v-subheader>Color</v-subheader>
      </v-flex>
      <v-flex xs2>
        <v-text-field
          name="input-1"
          disabled
          id="testing"
      ></v-text-field>
      </v-flex>
      <v-flex xs1>
        <v-subheader>Kms</v-subheader>
      </v-flex>
      <v-flex xs1>
        <v-text-field
          name="input-1"
          id="testing"
          maxlength="5"
      ></v-text-field>
      </v-flex>
    </v-layout>
    
<v-divider></v-divider>

<v-container fluid>
    <v-layout row wrap>
      <v-flex xs12 sm6>
        <v-menu
          lazy
          :close-on-content-click="false"
          v-model="menu"
          transition="scale-transition"
          offset-y
          full-width
          :nudge-left="40"
          max-width="290px"
        >
          <v-text-field
            slot="activator"
            label="Picker in menu"
            v-model="e3"
            prepend-icon="event"
            readonly
          ></v-text-field>
          <v-date-picker v-model="e3" no-title scrollable actions>
            <template scope="{ save, cancel }">
              <v-card-actions>
                <v-btn flat primary @click.native="cancel()">Cancel</v-btn>
                <v-btn flat primary @click.native="save()">Save</v-btn>
              </v-card-actions>
            </template>
          </v-date-picker>
        </v-menu>
      </v-flex>
      <v-flex xs12 sm6>
        <v-dialog
          persistent
          v-model="modal"
          lazy
          full-width
        >
          <v-text-field
            slot="activator"
            label="Picker in dialog"
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
    </v-layout>
  </v-container>
<v-divider></v-divider>
<v-layout row wrap>
      
      <v-flex xs12 sm6>
        <v-dialog
          persistent
          v-model="modal2"
          lazy
        >
          <v-text-field
            slot="activator"
            label="Hora Ingreso"
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
      <v-flex xs12 sm6>
        <v-dialog
          persistent
          v-model="modal3"
          lazy
        >
          <v-text-field
            slot="activator"
            label="Hora Salida"
            v-model="e7"
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
    <div>
    <v-card color="grey lighten-4" flat>
      <v-card-text>
        <!--<v-subheader>Light Theme</v-subheader>-->
        <v-container fluid>
          <v-layout row>
            <v-flex xs12>
              <v-text-field
                name="input-1"
                label="Observaciones"
                multi-line=true
                textarea
              ></v-text-field>
            </v-flex>
          </v-layout>
        </v-container>
      </v-card-text>
    </v-card>
    <v-card color="secondary" flat>
      <v-card-text>
        <v-subheader dark>Dark Theme</v-subheader>
        <v-container fluid>
          <v-layout row>
            <v-flex xs12>
              <v-text-field
                name="input-1"
                label="Label Text"
                textarea
                dark
              ></v-text-field>
            </v-flex>
          </v-layout>
        </v-container>
      </v-card-text>
    </v-card>
  </div>

<v-divider></v-divider>
    
  </v-form>
</template>

<script>
  export default {
    data () {
      return {
        e6: null,  //reloj
        modal2: false,
        e7: null,  //reloj 2
        modal3: false,
        
        cedula: null,
        nombre: null,
        telefono: null,
        direccion: null,
        
        placa: null,
        clientes: ['1065','1098','19872'],
        placas: [
          'MHK25D','RJO45A','XUY20D','MHE45E'],  
        valid: false,
        name: '',
        nameRules: [
          (v) => !!v || 'Name is required',
          (v) => v.length <= 10 || 'Name must be less than 10 characters'
        ],
        email: '',
        emailRules: [
          (v) => !!v || 'E-mail is required',
          (v) => /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(v) || 'E-mail must be valid'
        ]
      }
    },
    
    methods: {
      limpiarCliente(){
        this.cedula=""
        this.nombre=""
        this.telefono=""
        this.direccion=""
        document.getElementById(textCedula).focus();
      },
      limpiarMoto(){
        this.placa=""
      },
      guardar(){
        this.nombre="Carlos Andres Tamayo"
        this.telefono="  3136817175"
        this.direccion="calle 12 # 26-46"
      }
    },
  }
</script>