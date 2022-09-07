<template>
    <div class="box">
        <div class="columns">
            <div class="column is-8" role="form" aria-label="Formulário para criação de uma nova tarefa">
                <input type="text" class="input" placeholder="Qual tarefa você deseja iniciar?">
            </div>
            <div>
                <div class="column">
                    <TemporizadorPrincipal />
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
    components: { TemporizadorPrincipal }
})
</script>

<style scoped>
.linha-espacada {
    display: flex;
    align-items: center;
}
</style>
