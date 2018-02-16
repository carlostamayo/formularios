<template>
  <v-data-table
        v-bind:headers="headers"
        :items="items"
        hide-actions
        class="elevation-1"
    >
      <template slot="items" scope="props">
        <td style="font-weight: bold;" id="colum">{{ props.item.name }}</td>
        <td class="text-xs-center"><v-radio v-model="props.item.modelo" value="SI"></v-radio></td>
        <td class="text-xs-right"><v-radio v-model="props.item.modelo" value="NO"></v-radio></td>
      </template>
  </v-data-table>
</template>

<script>
  export default {
    data () {
      return {
        headers: [
          {
            text: 'ACCESORIOS',
            align: 'left',
            sortable: false,
            value: 'name'
          },
          { text: 'SI',sortable:false },
          { text: 'NO', sortable:false},
        ],
        items: [
          {
            name: 'HERRAMIENTAS', 
            modelo: "SI",
          },
          {
            name: 'ESPEJOS',
            modelo: "SI",
          },
          {
            name: 'LLAVES',
            modelo: "SI",
          },
          {
           name: 'TAPAS LATERALES',
            modelo: "SI",
          },
          {
            name: 'COCAS',
            modelo: "SI",
          },
          {
            name: 'TAPA GASOLINA Y/O ACEITE',
            modelo: "SI",
          },
          {
            name: 'GUARDACADENA',
            modelo: "SI",
          },
          
        ]
      }
    }
  }
</script>