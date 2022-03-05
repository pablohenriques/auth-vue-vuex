<template>
    <div>
        <nav class="navbar navbar-expand-lg navbar-bytebank">
            <a class="navbar-brand" href="#">ByteBank</a>
            <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="navbar-collapse collapse" id="navbarSupportedContent">
                <BarraNavegacaoQuandoLogado v-if="usuarioEstaLogado"/>
                <BarraNavegacaoQuandoDeslogado v-else/>
            </div>
        </nav>
    </div>
</template>

<script>

import BarraNavegacaoQuandoLogado from './BarraNavegacaoQuandoLogado';
import BarraNavegacaoQuandoDeslogado from './BarraNavegacaoQuandoDeslogado';

import { mapGetters } from 'vuex';

export default {

    components: {
        BarraNavegacaoQuandoLogado,
        BarraNavegacaoQuandoDeslogado
    },

    computed: {
    ...mapGetters(['usuarioEstaLogado'])
    }
}
</script>

<style>
</style>