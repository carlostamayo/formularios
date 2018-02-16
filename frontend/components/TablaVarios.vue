<template>
  <v-data-table
        v-bind:headers="headers"
        :items="items"
        hide-actions
        class="elevation-1"
    >
      <template slot="items" scope="props">
        <td style="font-weight: bold;" id="colum">{{ props.item.name }}</td>
        <td class="text-xs-center"><v-radio v-model="props.item.modelo" value="A"></v-radio></td>
        <td class="text-xs-right"><v-radio v-model="props.item.modelo" value="B"></v-radio></td>
        <td class="text-xs-right"><v-radio v-model="props.item.modelo" value="C"></v-radio></td>

      </template>
  </v-data-table>
  
</template>

<script>
  export default {
    data () {
      return {
        headers: [
          {
            text: 'A-Golpes B-Ruptura C-Buen Estado',
            align: 'left',
            sortable: false,
            value: 'name'
          },
          { text: 'A',sortable:false },
          { text: 'B', sortable:false},
          { text: 'C' ,sortable:false},
          
        ],
        items: [
          {
            name: 'TANQUE GASOLINA', 
            modelo: "A",
          },
          {
            name: 'TAPAS',
            modelo: "A",
          },
          {
            name: 'GUARDABARRO',
            modelo: "A",
          },
          {
           name: 'SILLIN',
            modelo: "A",
          },
          {
            name: 'MANIJAS',
            modelo: "A",
          },
          {
            name: 'EXOSTO',
            modelo: "A",
          },
          {
            name: 'FAROLA',
            modelo: "A",
          },
          
        ]
      }
    }
  }
</script>