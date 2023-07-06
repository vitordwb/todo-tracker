<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8"
           role="form"
           aria-label="Form to create a new task"
      >
        <input type="text"
               class="input"
               placeholder="Which task you want to star?"
        />
      </div>
      <div class="column">
        <StartStopTimer />
      </div>
    </div>
  </div>
</template>

<script lang='ts'>
import { defineComponent } from 'vue'
import StartStopTimer from '@/components/StartStopTimer.vue'

export default defineComponent({
  name: 'InputForm',
  components: {
    StartStopTimer
  }
});
</script>
