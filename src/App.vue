<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <SideBar />
    </div>

    <div class="column is-three-quarter">
      <FormCP />
    </div>

  </main>
</template>

<script>
import SideBar from './components/SideBar.vue';
import FormCP from './components/Form.vue';
export default {
  name: "App",
  components: { SideBar, FormCP }
}
</script>

<style>

</style>
