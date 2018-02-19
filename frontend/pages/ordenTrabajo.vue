<template>
  <div>
   <v-layout wrap>
    <v-btn dark fab class="cyan" @click.native="Agregar" v-model="abrir">
      <v-icon>add</v-icon>
    </v-btn>
    <v-flex x12 sm1></v-flex>
    <v-flex xs12 sm2>
      <v-text-field
          label="Cedula"
          v-model="cedula"
          @onkeypress="Agregar" 
      ></v-text-field>
      </v-flex xs12 sm1>
    <v-flex xs12 sm1></v-flex>
    <v-flex xs12 sm4>
      <v-text-field
         label="Nombre"
      ></v-text-field>
      </v-flex>
      <v-spacer></v-spacer>
      <v-btn icon>
        <v-icon>search</v-icon>
      </v-btn>
    </v-layout>
    <br><br>
    <template>
  <div>
    <v-data-table
      v-bind:headers="headers"
      v-bind:items="items"
      v-bind:search="search"
      v-bind:pagination.sync="pagination"
      hide-actions
      class="elevation-1"
    >
      <template slot="headerCell" scope="props">
        <span v-tooltip:bottom="{ 'html': props.header.text }">
          {{ props.header.text }}
        </span>
      </template>
      <template slot="items" scope="props">
        <td>{{ props.item.orden }}</td>
        <td  class="text-xs-right">{{ props.item.cedula }}</td>
        <td  class="text-xs-right">{{ props.item.nombre }}</td>
        <td  class="text-xs-right">{{ props.item.placa}}</td>
        <td  class="text-xs-right">{{ props.item.fecha }}</td>
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
    <div class="text-xs-center pt-2">
      <v-pagination v-model="pagination.page" :length="Math.ceil(this.items.length / pagination.rowsPerPage)"></v-pagination>
    </div>
  </div>
</template>

  </div>
</template>



<script>
  export default {
    data () {
      return {
        search: '',
        pagination: {},
        selected: [],
        headers: [
          {
            text: '# Orden',
            align: 'left',
            sortable: false,
            value: 'orden'
          },
          { text: 'Cedula', value: 'cedula' },
          { text: 'Nombre', value: 'nombre' },
          { text: 'Placa', value: 'placa' },
          { text: 'Fecha', value: 'fecha' },
          
        ],
        items: [
          {
            orden:"001",
            cedula:"1065864163",
            nombre:"Carlos Andres Tamayo Benjumea",
            placa:"mhk25d",
            fecha:"23-08-18"
          },
          {
            value: false,
            name: 'Ice cream sandwich',
            calories: 237,
            fat: 9.0,
            carbs: 37,
            protein: 4.3,
            sodium: 129,
            calcium: '8%',
            iron: '1%'
          },
          {
            value: false,
            name: 'Eclair',
            calories: 262,
            fat: 16.0,
            carbs: 23,
            protein: 6.0,
            sodium: 337,
            calcium: '6%',
            iron: '7%'
          },
          {
            value: false,
            name: 'Cupcake',
            calories: 305,
            fat: 3.7,
            carbs: 67,
            protein: 4.3,
            sodium: 413,
            calcium: '3%',
            iron: '8%'
          },
          {
            value: false,
            name: 'Gingerbread',
            calories: 356,
            fat: 16.0,
            carbs: 49,
            protein: 3.9,
            sodium: 327,
            calcium: '7%',
            iron: '16%'
          },
          {
            value: false,
            name: 'Jelly bean',
            calories: 375,
            fat: 0.0,
            carbs: 94,
            protein: 0.0,
            sodium: 50,
            calcium: '0%',
            iron: '0%'
          },
          {
            value: false,
            name: 'Lollipop',
            calories: 392,
            fat: 0.2,
            carbs: 98,
            protein: 0,
            sodium: 38,
            calcium: '0%',
            iron: '2%'
          },
          {
            value: false,
            name: 'Honeycomb',
            calories: 408,
            fat: 3.2,
            carbs: 87,
            protein: 6.5,
            sodium: 562,
            calcium: '0%',
            iron: '45%'
          },
          {
            value: false,
            name: 'Donut',
            calories: 452,
            fat: 25.0,
            carbs: 51,
            protein: 4.9,
            sodium: 326,
            calcium: '2%',
            iron: '22%'
          },
          {
            value: false,
            name: 'KitKat',
            calories: 518,
            fat: 26.0,
            carbs: 65,
            protein: 7,
            sodium: 54,
            calcium: '12%',
            iron: '6%'
          }
        ]
      }
    }
  }
</script>
