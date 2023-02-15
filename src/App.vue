<template>
  <main
    class="columns is-gapless is-multiline"
    :class="{ darkmode: darkModeActive }"
  >
    <div class="column is-one-quarter">
      <SideBar @onChangeTheme="changeTheme" />
    </div>

    <div class="column is-three-quarter content">
      <FormCP @onSaveTask="saveTask" />
      <div class="list">
        <TaskCP v-for="(task, index) in tasks" :key="index" :task="task" />
        <BoxCP v-if="isListEmpty">
          <span style="color: var(--text-primary)"
            >Você não está muito produtivo hoje =(</span
          >
        </BoxCP>
      </div>
    </div>
  </main>
  <FooterCP />
</template>

<script>
import SideBar from "./components/SideBar.vue";
import FormCP from "./components/Form.vue";
import TaskCP from "./components/Task.vue";
import BoxCP from "./components/Box.vue";
import FooterCP from "./components/Footer.vue";

export default {
  name: "App",
  components: { SideBar, FormCP, TaskCP, BoxCP, FooterCP },
  data() {
    return {
      tasks: [],
      darkModeActive: false,
    };
  },
  computed: {
    isListEmpty() {
      return this.tasks.length == 0;
    },
  },
  methods: {
    saveTask(task) {
      this.tasks.push(task);
    },
    changeTheme(darkMode) {
      this.darkModeActive = darkMode;
    },
  },
};
</script>

<style>
.list {
  padding: 1.25rem;
}

main {
  --bg-primary: #fff;
  --text-primary: #000;
  --box-bg: #faf0ca;
}

main.darkmode {
  --bg-primary: #2b2d42;
  --text-primary: #ddd;
  --box-bg: #666;
}

.content {
  background-color: var(--bg-primary);
}
</style>
