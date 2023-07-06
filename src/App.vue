<template>
  <main class="columns is-gapless is-multiline">
    <div class="colum is-one-quarter">
      <SideBar />
    </div>
    <div class="colum is-three-quarter">
      <InputForm />
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import SideBar from '@/components/SideBar.vue'
import InputForm from '@/components/InputForm.vue'

export default defineComponent({
  name: 'App',
  components: {
    InputForm,
    SideBar
  },
});
</script>

<style>

</style>
