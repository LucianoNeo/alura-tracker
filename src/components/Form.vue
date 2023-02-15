<template>
  <div class="box form">
    <div class="columns">
      <div class="column is-8" role="form" aria-label="Formulário para criação de uma nova tarefa">
        <input type="text" class="input" placeholder="Qual tarefa você deseja iniciar?" v-model="description">
      </div>
      <div class="column">
        <TimerCP @TimerEnded="endTask" />
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'
import TimerCP from './Timer.vue'

export default defineComponent({
  name: 'FormCP',
  emits: ['onSaveTask'],
  data () {
    return {
      description: ''
    }
  },
  components: {
    TimerCP
  },
  methods: {
    endTask(elapsedTime) {
    this.$emit('onSaveTask', {
      description: this.description,
      elapsedTime: elapsedTime
    })
      this.description =''
    }
  }
})


</script>

<style>
.form{
  color: var(--text-primary);
  background-color: var(--bg-primary)
}
</style>