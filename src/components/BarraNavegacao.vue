<template>
    <div>
        <nav class="navbar navbar-expand-lg navbar-bytebank">
            <a class="navbar-brand" href="#">ByteBank</a>
            <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="navbar-collapse collapse" id="navbarSupportedContent">
                <ul class="navbar-nav mr-auto" v-if="usuarioEstaLogado">
                    <li class="nav-item">
                        <router-link class="nav-link" to="/">Home</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link to="/gerentes" class="nav-link">
                            Gerentes
                        </router-link>
                    </li>
                    <li class="nav-item">
                        <a href="#" @click.prevent="efetuarLogout" class="nav-link">
                            Logout
                        </a>
                    </li>
                </ul>
                <ul class="navbar-nav mr-auto" v-else>
                    <li class="nav-item">
                        <router-link class="nav-link" to="/login">Login</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link to="/cadastre-se" class="nav-link">Registre-se</router-link>
                    </li>
                </ul>
            </div>
        </nav>
    </div>
</template>

<script>
export default {
    methods: {
        efetuarLogout() {
            localStorage.removeItem('token');
            this.$router.push({ name: 'login' });
        }
    },

    computed: {
      usuarioEstaLogado() {
          return Boolean(localStorage.getItem('token'));
      }
    }
}
</script>

<style>
</style>