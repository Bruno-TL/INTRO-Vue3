<template>
    <div>
        <HelloWorld msg="Hello world do life cycle" v-if="showHeader"/>
        <p>Life Circle</p>
        <button @click=" showHeader = !showHeader">Mostre e apague o hello world do life cyrcle</button>
    </div>
    
</template>

<script>
import HelloWorld from './HelloWorld.vue';
    export default {
        components: {HelloWorld},
        data(){
            return {
                name: 'T.Bruno',
                showHeader: true,
            }
        },
        //  Criação
            // Preparar o componente
            // Ajax, inicializar algumas variáveis
            // Não tem acesso ao template (DOM)
        //  Montagem
            // Inicializar um lib externa (new Lib())
            // Precisa  de acesso ao template (DOM)
            // Tem acesso ao template (DOM)
        //  Atualização
            // Debug
            // Update
        //  Desmontagem
            // Remover tudo o que for necessário (lib->destroy())
            // para liberar memória


        // HOOKS 
        // Criação(Antes da criação)
        beforeCreate(){
            console.log('beforeCreate');
            console.log('Estado: ',this.name);
            // Não irá aparecer o name pq n tem acesso ao estado.
            console.log('DOM: ', this.$el);
        },
        created(){
            console.log('Create');
            console.log('Estado: ',this.name);
            console.log('DOM: ', this.$el);
        },

        // Montagem (depois da criação)
        beforeMount(){
            console.log('beforeMount');
            console.log('Estado: ',this.name);
            console.log('DOM: ', this.$el);
        },
        mounted(){
            console.log('mount');
            console.log('Estado: ',this.name);
            console.log('DOM: ', this.$el);
            // Só aparecerar os valores só quando já montados/ mounted;
        },

        // Desmontagem
        beforeUnmount(){
            console.log('beforeUnmount');
        },
        unmounted(){
            console.log('unmount');
        },

        // Usado para Debug
        beforeUpdate(){

        },
        updated(){

        },

        watch: {

        },

        computed: {
            
        },

        methods: {

        }
    }
</script>

<style>

</style>