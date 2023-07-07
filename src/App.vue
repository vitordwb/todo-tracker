<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <SideBar />
    </div>
    <div class="column is-three-quarter">
      <InputForm @toSaveTask="saveTask"/>
      <div class="tasks-list">
        <TasksList v-for="(task, index) in tasks" :key="index" :task="task"/>
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import SideBar from '@/components/SideBar.vue'
import InputForm from '@/components/InputForm.vue'
import TasksList from '@/components/TasksList.vue'
import ITask from '@/interfaces/ITask'

export default defineComponent({
  name: 'App',
  components: {
    TasksList,
    InputForm,
    SideBar
  },
  data() {
    return {
      tasks: [] as ITask[],
    }
  },
  methods: {
    saveTask(task: ITask) {
      this.tasks.push(task);
    }
  },
});
</script>

<style>
.tasks-list {
  padding: 1.25rem;
}
</style>
