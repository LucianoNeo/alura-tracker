<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <SideBar />
    </div>

    <div class="column is-three-quarter">
      <FormCP @onSaveTask="saveTask" />
      <div class="list">
        <TaskCP v-for="(task, index) in tasks" :key="index" :task="task" />
        <BoxCP v-if="isListEmpty">
          Você não está muito produtivo hoje =(
        </BoxCP>
      </div>
    </div>
  </main>
</template>

<script>
import SideBar from './components/SideBar.vue';
import FormCP from './components/Form.vue';
import TaskCP from './components/Task.vue';
import BoxCP from './components/Box.vue';

export default {
  name: "App",
  components: { SideBar, FormCP, TaskCP,BoxCP },
  data() {
    return {
      tasks: []
    }
  },
  computed:{
    isListEmpty(){
      return this.tasks.length == 0
    }
  },
  methods: {
    saveTask(task) {
      this.tasks.push(task)
    }
  }
}
</script>

<style>
.list {
  padding: 1.25rem;
}
</style>
