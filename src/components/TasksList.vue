<template>
  <div class="box has-text-weight-bold">
    <div class="columns">
      <div class="column is-7">
        {{ task.description || 'Task with no description' }}
      </div>
      <div class="column">
        <StopwatchTimer :timeInSeconds="task.durationInSeconds"/>
      </div>
    </div>
  </div>
</template>

<script lang='ts'>
import { defineComponent, PropType } from 'vue'
import StopwatchTimer from '@/components/StopwatchTimer.vue'
import ITask from "@/interfaces/ITask";

export default defineComponent({
  name: 'TasksList',
  components: {
    StopwatchTimer
  },
  props: {
    task: {
      type: Object as PropType<ITask>,
      required: true,
    }
  },
});
</script>

<style scoped>
.box {
  background: #FAF0CA;
}
</style>
