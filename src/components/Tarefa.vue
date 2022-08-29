<template>
    <Box>
        <div class="columns">
            <div class="column is-7">
                {{ tarefa.descricao || 'Tarefa sem descrição' }}
            </div>
            <div class="column">
                <cronometro :tempoEmSegundos="tarefa.duracaoEmSegundos" />
            </div>
        </div>
    </Box>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import Cronometro from './Cronometro.vue';
import iTarefa from '../interfaces/iTarefa'
import Box from './Box.vue';

export default defineComponent({
    name: 'TarEfa',
    components: {
        Cronometro,
        Box
    },
    props: {
        tarefa: {
            type: Object as PropType<iTarefa>,
            required: true
        }
    }
})

</script>