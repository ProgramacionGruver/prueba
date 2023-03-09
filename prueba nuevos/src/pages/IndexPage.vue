<template>
  <q-page class="flex flex-center">

    <div class="column">
      
      <q-btn color="primary" icon="add" @click="sumarContador" />
      <q-btn class="q-mt-md" color="primary" icon="clear" @click="contador = 0" />

      <div align="center">
        <div class="q-mt-xl text-h2"> {{ contador }}</div>
      </div>

      <div class="q-mt-xl">
        <q-btn color="primary" label="Abrir modal" icon="open_with" @click="abrirModal" />
      </div>

    </div>

  </q-page>

  <ModalPrueba ref="modal"></ModalPrueba>
</template>

<script>
import { ref } from 'vue'
import ModalPrueba from 'src/components/ModalPrueba.vue'

export default {
  components: {
    ModalPrueba
  },

  setup() {
    const contador = ref(0)
    const modal = ref(null)

    const sumarContador = () => {
      contador.value++
      console.log(contador.value)
    }

    const abrirModal = () => {
      modal.value.abrir(contador.value)
    }

    return {
      contador,
      sumarContador,
      abrirModal,
      modal
    }

  },
}
</script>

<style>

</style>
