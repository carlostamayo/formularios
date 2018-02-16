<template>
  <v-tabs dark fixed centered>
    <v-tabs-bar slot="activators" class="blue-grey darken-4">
      <v-tabs-slider class="white"></v-tabs-slider>
      <v-tabs-item
        :href="'#tab-1'">
        INFORMACION
      </v-tabs-item>
      <v-tabs-item
        :href="'#tab-2'">
        SOLICITADOS
      </v-tabs-item>
      <v-tabs-item
        :href="'#tab-3'">
        ACCESORIOS
      </v-tabs-item>
      <v-tabs-item
        :href="'#tab-4'">
        VARIOS
      </v-tabs-item>
      <v-tabs-item
        :href="'#tab-5'">
        SISTEMA ELECTRICO
      </v-tabs-item>
    </v-tabs-bar>
    <v-tabs-content
      :id="'tab-1'">
      <v-card flat>
        <v-card-text>
          <informacion></informacion>
        </v-card-text>
      </v-card>
    </v-tabs-content>
    <v-tabs-content
      :id="'tab-2'">
      <v-card flat>
        <v-card-text>
          <tabla-solicitados></tabla-solicitados>
        </v-card-text>
      </v-card>
    </v-tabs-content>
    <v-tabs-content
      :id="'tab-3'">
      <v-card flat>
        <v-card-text>
          <tabla-accesorios></tabla-accesorios>
        </v-card-text>
      </v-card>
    </v-tabs-content>
    <v-tabs-content
      :id="'tab-4'">
      <v-card flat>
        <v-card-text>
          <tabla-varios></tabla-varios>
        </v-card-text>
      </v-card>
    </v-tabs-content>
    <v-tabs-content
      :id="'tab-5'">
      <v-card flat>
        <v-card-text>
          <tabla-sistema-electrico></tabla-sistema-electrico>
        </v-card-text>
      </v-card>
    </v-tabs-content>
  </v-tabs>
</template>

<script>
  import TablaAccesorios from '~/components/TablaAccesorios.vue'
  import TablaVarios from '~/components/TablaVarios.vue'
  import TablaSistemaElectrico from '~/components/TablaSistemaElectrico.vue'
  import informacion from '~/components/informacion.vue'
  import TablaSolicitados from '~/components/TablaSolicitados.vue'
  export default {
    data () {
      return {
        
      }
    },
    components: {
      TablaAccesorios,
      TablaVarios,
      TablaSistemaElectrico,
      informacion,
      TablaSolicitados
    }
  }
</script>
