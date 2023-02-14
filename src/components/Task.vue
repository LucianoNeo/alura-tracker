<template>
    <BoxCP>
        <div class="columns">
            <div class="column is-7">
                {{task.description || 'Tarefa sem descrição'}}
            </div>
            <div class="column">
                <StopWatch :timeInSeconds='task.elapsedTime'/>
            </div>
        </div>
    </BoxCP>
</template>
<script>

    import {defineComponent} from 'vue'
    import StopWatch from './StopWatch.vue'
    import BoxCP from './Box.vue'

    export default defineComponent({
        name: 'TaskCP',
        components: {StopWatch,BoxCP},
        props:{
            task:{
                type: Object,
                required: true
            }
        }
    })
</script>

