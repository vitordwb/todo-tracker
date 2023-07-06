<template>
  <div class="box">
    <div class="columns">
      <div class="columns is-8" role="form" aria-label="Formulário para criaçao de uma nova tarefa">
        <input type="text" class="input" placeholder="Qual tarefa deseja iniciar?">
      </div>
      <div class="column">
        <section>
          <strong>00:00:00</strong>
        </section>
        <button class="button">
          <span class="icon">
            <i class="fa fas-play"></i>
          </span>
          <span>play</span>
        </button>
        <button class="button">
          <span class="icon">
            <i class="fa fas-stop"></i>
          </span>
          <span>stop</span>
        </button>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'InputForm'
})
</script>
