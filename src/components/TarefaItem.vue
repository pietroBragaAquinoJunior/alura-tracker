<template>
    <div class="box has-text-weight-bold">
        <div class="columns">
            <div class="column is-7">
                {{tarefa.descricao}}
            </div>
            <div class="column">
                <CronometroPrincipal :tempoEmSegundos="tarefa.duracaoEmSegundos" />
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import ITarefa from '@/interfaces/ITarefa';
import { defineComponent, PropType } from 'vue';
import CronometroPrincipal from './CronometroPrincipal.vue';
export default defineComponent({
    name: 'TarefaItem',
    components: { CronometroPrincipal },
    props: {
        tarefa: {
            type: Object as PropType<ITarefa>,
            required: true
        }
    }
});
</script>
    
<style scoped>
.box {
    background: #FAF0CA;
}
</style>