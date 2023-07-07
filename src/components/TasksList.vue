<template>
  <TaskBox>
    <div class="columns">
      <div class="column is-7">
        {{ task.description || 'Task with no description' }}
      </div>
      <div class="column">
        <StopwatchTimer :timeInSeconds="task.durationInSeconds"/>
      </div>
    </div>
  </TaskBox>
</template>

<script lang='ts'>
import { defineComponent, PropType } from 'vue'
import StopwatchTimer from '@/components/StopwatchTimer.vue'
import TaskBox from '@/components/TaskBox.vue'
import ITask from "@/interfaces/ITask";

export default defineComponent({
  name: 'TasksList',
  components: {
    TaskBox,
    StopwatchTimer,
  },
  props: {
    task: {
      type: Object as PropType<ITask>,
      required: true,
    }
  },
});
</script>
