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
            name: 'Cambio de Aceite', 
            modelo: "Solicitado",
            value: true, 
          },
          {
            name: 'Calibrar Valvulas',
            modelo: "SI",
          },
          {
            name: 'Cambiar Filtro Aceite',
            modelo: "SI",
          },
          {
           name: 'Cambiar Bujia',
            modelo: "SI",
          },
          {
            name: 'Cambia Aceite Hidraulico',
            modelo: "SI",
          },
          {
            name: 'Cambiar Liquido Frenos',
            modelo: "SI",
          },
          {
            name: 'Cambiar Correa Transmision',
            modelo: "SI",
          },
          
        ]
      }
    }
  }
</script>