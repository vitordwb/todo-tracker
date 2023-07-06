<template>
  <main class="columns is-gapless is-multiline">
    <div class="colum is-one-quarter">
      <BarraLateral />
    </div>
    <div class="colum is-three-quarter">
      <InputForm />
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from '@/components/BarraLateral.vue'
import InputForm from '@/components/InputForm.vue'

export default defineComponent({
  name: 'App',
  components: {
    InputForm,
    BarraLateral
  },
});
</script>

<style>

</style>
