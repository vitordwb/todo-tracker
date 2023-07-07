<template>
  <main class="columns is-gapless is-multiline dark-mode">
    <div class="column is-one-quarter">
      <SideBar />
    </div>
    <div class="column is-three-quarter content">
      <InputForm @toSaveTask="saveTask"/>
      <div class="tasks-list">
        <TasksList v-for="(task, index) in tasks" :key="index" :task="task"/>
        <TaskBox v-if="isTasksListEmpty">
          You have not been so productive today :(
        </TaskBox>
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import SideBar from '@/components/SideBar.vue'
import InputForm from '@/components/InputForm.vue'
import TasksList from '@/components/TasksList.vue'
import TaskBox from '@/components/TaskBox.vue'
import ITask from '@/interfaces/ITask'

export default defineComponent({
  name: 'App',
  components: {
    TaskBox,
    TasksList,
    InputForm,
    SideBar
  },
  data() {
    return {
      tasks: [] as ITask[],
    }
  },
  computed: {
    isTasksListEmpty() : boolean {
      return this.tasks.length === 0
    },
  },
  methods: {
    saveTask(task: ITask) {
      this.tasks.push(task);
    },
  },
});
</script>

<style>
.tasks-list {
  padding: 1.25rem;
}
main {
  --bg-primary: #fff;
  --text-primary: #000;
}
main.dark-mode {
  --bg-primary: #2b2d42;
  --text-primary: #ddd;
}
.content {
  background-color: var(--bg-primary);
}
</style>
