<template>
  <header>
    <h1>
      <img src="../assets/logo.png" alt="" srcset="" />
    </h1>
    <button class="button" @click="changeTheme">
      {{ ButtonText }}
    </button>
  </header>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "SideBar",
  emits: ["onChangeTheme"],
  computed: {
    ButtonText() {
      if (this.darkModeActive) {
        return "Desativar Modo Escuro";
      }
      return "Ativar Modo Escuro";
    },
  },
  data() {
    return {
      darkModeActive: false,
    };
  },
  methods: {
    changeTheme() {
      this.darkModeActive = !this.darkModeActive;
      this.$emit("onChangeTheme", this.darkModeActive);
    },
  },
});
</script>

<style scoped>
header {
  padding: 1rem;
  background: #0d3b66;
  width: 100%;
  height: 100vh;
  text-align: center;
}

@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}
</style>
