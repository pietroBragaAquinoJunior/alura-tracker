<template>
    <div class="box">
        <div class="columns">
            <div class="column is-8" role="form" aria-label="Formulário para criação de uma nova tarefa">
                <input type="text" class="input" placeholder="Qual tarefa você deseja iniciar?" v-model="descricao">
            </div>
            <div>
                <div class="column">
                    <TemporizadorPrincipal @ao-temporizador-finalizado="finalizarTarefa" />
                </div>
            </div>
        </div>
    </div>
</template>
  
<script lang="ts">
import { defineComponent } from 'vue'
import TemporizadorPrincipal from './TemporizadorPrincipal.vue';

export default defineComponent({
    name: "FormularioPrincipal",
    emits: ['aoSalvarTarefa'],
    components: { TemporizadorPrincipal },
    data () {
        return {
            descricao: ''
        }
    },
    methods : {
        finalizarTarefa(tempoDecorrido: number) : void{
            this.$emit('aoSalvarTarefa', {
                duracaoEmSegundos: tempoDecorrido,
                descricao: this.descricao
            })
            this.descricao = ''
        }
    }
})
</script>

<style scoped>
.linha-espacada {
    display: flex;
    align-items: center;
}
</style>
