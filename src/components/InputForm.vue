<template>
  <div class="box form">
    <div class="columns">
      <div class="column is-8"
           role="form"
           aria-label="Form to create a new task"
      >
        <input type="text"
               class="input"
               placeholder="Which task you want to star?"
               v-model="description"
        />
      </div>
      <div class="column">
        <StartStopTimer @toTimerFinish="finishTask"/>
      </div>
    </div>
  </div>
</template>

<script lang='ts'>
import { defineComponent } from 'vue'
import StartStopTimer from '@/components/StartStopTimer.vue'

export default defineComponent({
  name: 'InputForm',
  emits: ['toSaveTask'],
  components: {
    StartStopTimer
  },
  data() {
    return {
      description: '',
    }
  },
  methods: {
    finishTask(timeSpent: number) : void {
      this.$emit('toSaveTask', {
        durationInSeconds: timeSpent,
        description: this.description
      })
      this.description = '';
    }
  },
});
</script>

<style>
.form {
  color: var(--text-primary);
  background-color: var(--bg-primary);
}
</style>
