<template>
  <v-data-table
        v-bind:headers="headers"
        :items="items"
        hide-actions
        class="elevation-1"
    >
      <template slot="items" scope="props">
        <td style="font-weight: bold;" id="colum">{{ props.item.name }}</td>
        <td class="text-xs-center"><v-radio label="B" v-model="props.item.modelo" value="B"></v-radio></td>
        <td class="text-xs-right"><v-radio label="R" v-model="props.item.modelo" value="R"></v-radio></td>
        <td class="text-xs-right"><v-radio label="M" v-model="props.item.modelo" value="M"></v-radio></td>

      </template>
  </v-data-table>
</template>

<script>
  export default {
    data () {
      return {
        headers: [
          {
            text: 'SISTEMA ELECTRICO B-bueno R-regular M-malo',
            align: 'left',
            sortable: false,
            value: 'name'
          },
          /*{ text: 'A',sortable:false },
          { text: 'B', sortable:false},
          { text: 'C' ,sortable:false},*/
          
        ],
        items: [
          {
            name: 'LUZ DIRECCIONAL', 
            modelo: "B",
          },
          {
            name: 'STOP',
            modelo: "B",
          },
          {
            name: 'PITO',
            modelo: "B",
          },
          {
           name: 'BATERIA',
            modelo: "B",
          },
          {
            name: 'LUZ FAROLA',
            modelo: "B",
          },
          {
            name: 'LUZ FRENO',
            modelo: "B",
          },
          {
            name: 'LUZ PILOTO',
            modelo: "B",
          },
          
        ]
      }
    }
  }
</script>