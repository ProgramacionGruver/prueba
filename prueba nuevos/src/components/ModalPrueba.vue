<template>
  <q-dialog v-model="abrirModal">
    <q-card class="full-width">
      <q-card-section class="bg-primary text-white row items-center q-pb-none">

        <h2 class="text-h6" v-if="contador > 10">Tu contador es mayor que 10</h2>
        
        <h2 class="text-h6" v-else>Tu contador es menor a 10</h2>
        
        <q-space />
        <q-btn icon="close" flat round dense v-close-popup />
      </q-card-section>
      <q-card-section>
        <div>Tu contador es: {{ contador }} </div>
      </q-card-section>
    </q-card>
  </q-dialog>
</template>

<script>
import { ref, } from 'vue'

export default {
  setup() {

    const abrirModal = ref(false)
    const contador = ref(0)

    const abrir = (cuentaActual) => {
      contador.value = cuentaActual
      abrirModal.value = true
    }

    return {
      abrirModal,
      abrir,
      contador
    }
  },
}
</script>

<style></style>