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


export default {

    components: {
        BarraNavegacaoQuandoLogado,
        BarraNavegacaoQuandoDeslogado
    },

    computed: {
      usuarioEstaLogado() {
        //   return Boolean(localStorage.getItem('token'));
        // return Boolean(this.$store.state.token);
        return this.$store.getters.usuarioEstaLogado;
      }
    }
}
</script>

<style>
</style>