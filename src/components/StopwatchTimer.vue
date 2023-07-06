<template>
  <section>
    <strong>{{ timeSpent }}</strong>
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'StopwatchTimer',
  props: {
    timeInSeconds: {
      type: Number,
      default: 0
    }
  },
  computed: {
    timeSpent(): string {
      return new Date(this.timeInSeconds * 1000).toISOString().substr(11, 8);
    }
  },
})
</script>
