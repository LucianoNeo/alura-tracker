<template>
  <div class="box has-text-weight-bold" :style="customStyle">
    <slot></slot>
  </div>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "BoxCP",
  data() {
    return {
      customStyle: {
        background: "var(--box-bg)",
      },
    };
  },
});
</script>
