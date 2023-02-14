<template>
    <header>
        <h1 class="has-text-centered">
            <img src="../assets/logo.png" alt="" srcset="">
        </h1>
    </header>
</template>

<script>
import {defineComponent} from 'vue'

export default defineComponent({
    name: 'SideBar'
})
</script>

<style scoped>
header {
  padding: 1rem;
  background: #0d3b66;
  width: 100%;
  height: 100vh;
}
@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}
</style>