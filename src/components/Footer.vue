<template>
  <footer class="footer" :style="Style">
    <span style="color: var(--text-primary); font-weight: bold"
      >Developed by LucianoNeo with Vue.JS 3.2.13</span
    >
  </footer>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "FooterCP",
  data() {
    return {
      Style: {
        backgroundColor: "var(--bg-primary)",
        textAlign: "center",
        width: "100vw",
        padding: "10px",
        position: "absolute",
        bottom: 0,
      },
      SpanStyle: {
        color: "var(--text-primary)",
        fontWeight: "bold",
      },
    };
  },
});
</script>
