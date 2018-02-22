<template>
  <div>
   <v-data-table
        v-bind:headers="headers"
        :items="items"
        hide-actions
        class="elevation-1"
    >
      <template slot="items" scope="props">
        <td style="font-weight: bold;" id="colum">{{ props.item.name |uppercase }}</td>
        <td class="text-xs-center"><v-checkbox label="" 
                        v-model="props.item.modelo"
                        color="secondary"
                        value="true"
                        hide-details></v-checkbox></td>
      </template>
   </v-data-table>
   <br><br>
   
   <!--<v-layout row>
    <v-data-table
        v-bind:headers="headers2"
        :items="items2"
        hide-actions
        class="elevation-1"
    >
      <template slot="items" scope="props">
        <td style="font-weight: bold;">{{ props.item.name }}</td>
        <td class="text-xs-center"><v-radio label="SI" v-model="props.item.modelo" value="SI"></v-radio></td>
        <td class="text-xs-right"><v-radio label="NO" v-model="props.item.modelo" value="NO"></v-radio></td>
      </template>
    </v-data-table>
   </v-layout>-->
   <p>Cliente Solicita</p>
   <v-layout v-for="(item, i) in items2">
     <v-text-field
     label="*"
    >{{item.name}}</v-text-field>
   </v-layout>
  </div>

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
        ],
        items2: ["1","2","3","4","5"],
      }
    }
  }
</script>
