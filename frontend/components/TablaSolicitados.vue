<template>
  <v-data-table
        v-bind:headers="headers"
        :items="items"
        hide-actions
        class="elevation-1"
    >
      <template slot="items" scope="props">
        <td style="font-weight: bold;" id="colum">{{ props.item.name }}</td>
        <td class="text-xs-center"><v-checkbox label="" 
                        v-model="props.item.modelo"
                        color="secondary"
                        value="true"
                        hide-details></v-checkbox></td>
      </template>
  </v-data-table>
</template>

<script>
  export default {
    data () {
      return {
        headers: [
          {
            text: 'Trabajos Solicitados',
            align: 'left',
            sortable: false,
            value: 'name'
          },
          { text: 'Solicitado',sortable:false },
        ],
        items: [
          {
            name: 'HERRAMIENTAS', 
            modelo: "Solicitado",
            value: true, 
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