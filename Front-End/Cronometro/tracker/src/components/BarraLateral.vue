<template>
    <header>
        <h1>
            <img class="img_logo" src="../assets/logo.png" alt="">
        </h1>
        <button class="button botao" @click="alterarTema">
            {{textoBotao}}
        </button>
    </header>
</template>

<script lang="ts">
    import { defineComponent } from "vue";

    export default defineComponent({
        name: 'BarraLateral',
        emits: ['aoTemaAlterado'],
        data () {
            return {
                modoEscuroAtivo: false
            }
        },
        computed: {
            textoBotao () {
                if(this.modoEscuroAtivo) {
                    return `Modo Normal`
                }
                return `Modo Escuro`
            }
        },
        methods: {
            alterarTema () {
                this.modoEscuroAtivo = !this.modoEscuroAtivo
                this.$emit('aoTemaAlterado', this.modoEscuroAtivo)
            }
        }
    })
</script>

<style scoped>
header {
    background: #0d3b66;
    width: 100%;
    height: 100vh;
    text-align: center;
}

.img_logo {
    width: 90px;
    margin-top: 5%;
}

.botao {
    margin: 10%;
}

@media only screen and (max-width: 768px) {
    header {
        padding: 2.5rem;
        height: auto;
    }

    .img_logo {
    width: 100px;
    align-self: center;
}
}

</style>