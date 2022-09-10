<template>
    <BoxPrincipal>
        <div class="columns">
            <div class="column is-7">
                {{tarefa.descricao || "Tarefa sem descrição"}}
            </div>
            <div class="column">
                <CronometroPrincipal :tempoEmSegundos="tarefa.duracaoEmSegundos" />
            </div>
        </div>
    </BoxPrincipal>
</template>

<script lang="ts">
import ITarefa from '@/interfaces/ITarefa';
import { defineComponent, PropType } from 'vue';
import CronometroPrincipal from './CronometroPrincipal.vue';
import BoxPrincipal from './BoxPrincipal.vue';
export default defineComponent({
    name: 'TarefaItem',
    components: { CronometroPrincipal, BoxPrincipal },
    props: {
        tarefa: {
            type: Object as PropType<ITarefa>,
            required: true
        }
    }
});
</script>
    
<style scoped>

</style>