<template>
  <div
    class="is-flex is-align-items-center is-justify-content-space-between"
  >
    <StopwatchTimer :timeInSeconds="timeInSeconds"/>
    <button class="button" @click="start">
      <span class="icon">
        <i class="fas fa-play"></i>
      </span>
      <span>play</span>
    </button>
    <button class="button" @click="stop">
      <span class="icon">
        <i class="fas fa-stop"></i>
      </span>
      <span>stop</span>
    </button>
  </div>
</template>

<script lang='ts'>
import { defineComponent } from 'vue'
import StopwatchTimer from '@/components/StopwatchTimer.vue'

export default defineComponent({
  name: 'StartStopTimer',
  components: {
    StopwatchTimer
  },
  data() {
    return {
      timeInSeconds: 0,
      stopwatch: 0
    }
  },
  methods: {
    start() {
      this.stopwatch = setInterval(()=> {
        this.timeInSeconds++
      }, 1000)
    },
    stop() {
      clearInterval(this.stopwatch);
    },
  }
})
</script>
