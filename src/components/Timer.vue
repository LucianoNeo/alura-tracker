<template>
  <div class="is-flex is-align-items-center is-justify-content-space-between">
    <StopWatch :timeInSeconds="timeInSeconds" />
    <button class="button" @click="start" :disabled="running">
      <span class="icon">
        <i class="fas fa-play"></i>
      </span>
      <span>play</span>
    </button>
    <button class="button" @click="end" :disabled="!running">
      <span class="icon">
        <i class="fas fa-stop"></i>
      </span>
      <span>stop</span>
    </button>

  </div>
</template>

<script>
import { defineComponent } from 'vue'
import StopWatch from './StopWatch.vue'
export default defineComponent({
  name: 'TimerCP',
  emits: [
    'TimerEnded'
  ],
  components: {
    StopWatch
  },
  data() {
    return {
      timeInSeconds: 0,
      stopwatch: 0,
      running: false,
    }
  },

  methods: {

    start() {
      this.running = true;
      this.stopwatch = setInterval(() => {
        this.timeInSeconds++
      }, 1000)
    },

    end() {
      this.running = false;
      clearInterval(this.stopwatch)
      this.$emit('TimerEnded', this.timeInSeconds)
      this.timeInSeconds = 0
    }
  }



})
</script>