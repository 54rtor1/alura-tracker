<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8" role="form" aria-label="New task form">
        <input
          type="text"
          class="input"
          placeholder="Which task would you like to start?"
          v-model="description"
        />
      </div>
      <div class="column">
        <Temporizador @aoTemporizadorFinalizado="finalizarTarefa"/>
      </div>
    </div>
  </div>
</template>

<script lang="ts">

import { defineComponent } from 'vue'
import Temporizador from './Temporizador.vue'

export default defineComponent({
  name: 'Formulario',
  components: {
    Temporizador
  },
  data () {
    return {
      description: ''
    }
  },
  methods: {
    finalizarTarefa (tempoDecorrido: number) : void {
      console.log('task time', tempoDecorrido)
      console.log('task description', this.description)
      this.description = ''
    }
  }
});

</script>

<style>
</style>
