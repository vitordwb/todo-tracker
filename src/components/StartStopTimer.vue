<template>
  <div
    class="is-flex is-align-items-center is-justify-content-space-between"
  >
    <StopwatchTimer :timeInSeconds="timeInSeconds"/>
    <button class="button" @click="start" :disabled="stopwatchRunning">
      <span class="icon">
        <i class="fas fa-play"></i>
      </span>
      <span>play</span>
    </button>
    <button class="button" @click="stop" :disabled="!stopwatchRunning">
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
  emits: ['toTimerFinish'],
  components: {
    StopwatchTimer
  },
  data() {
    return {
      timeInSeconds: 0,
      stopwatch: 0,
      stopwatchRunning: false,
    }
  },
  methods: {
    start() {
      this.stopwatchRunning = true;
      this.stopwatch = setInterval(()=> {
        this.timeInSeconds++
      }, 1000);
    },
    stop() {
      this.stopwatchRunning = false;
      clearInterval(this.stopwatch);
      this.$emit('toTimerFinish', this.timeInSeconds);
      this.timeInSeconds = 0;
    },
  }
})
</script>
