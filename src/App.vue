<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BarraLateral/>
    </div>
    <div class="column is-three-quarter">
      <FormularioPrincipal @aoSalvarTarefa="salvarTarefa" />
      <div class="lista">
        <TarefaItem v-for="(tarefa, index) in tarefas" :key="index" :tarefa="tarefa" />
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from './components/BarraLateral.vue';
import FormularioPrincipal from './components/Formulario.vue';
import TarefaItem from './components/TarefaItem.vue';
import ITarefa from './interfaces/ITarefa';
export default defineComponent({
    name: "App",
    components: { BarraLateral, FormularioPrincipal, TarefaItem },
    data () {
      return {
        tarefas: [] as ITarefa[]
      }
    },
    methods : {
      salvarTarefa (tarefa: ITarefa) {
        this.tarefas.push(tarefa)
      }
    }
});
</script>

<style>
  .list {
    padding: 1.25rem;
}
</style>
