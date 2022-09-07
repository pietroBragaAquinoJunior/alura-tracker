

<template>
    <div class="linha-espacada">
        <CronometroPrincipal :tempoEmSegundos="tempoEmSegundos" />
        <button class="button" @click="iniciar">
            <span class="icon">
                <i class="fas fa-play"></i>
            </span>
            <span>play</span>
        </button>
        <button class="button" @click="finalizar">
            <span class="icon">
                <i class="fas fa-stop"></i>
            </span>
            <span>stop</span>
        </button>
    </div>
</template>
  
<script lang="ts">
import { defineComponent } from 'vue'
import CronometroPrincipal from './CronometroPrincipal.vue';

export default defineComponent({
    name: "TemporizadorPrincipal",
    data() {
        return {
            tempoEmSegundos: 0,
            cronometro: 0
        };
    },

    methods: {
        iniciar() {
            this.cronometro = setInterval(() => {
                this.tempoEmSegundos += 1;
            }, 1000);
        },
        finalizar() {
            clearInterval(this.cronometro);
        }
    },
    components: { CronometroPrincipal }
})
</script>

<style scoped>

</style>
