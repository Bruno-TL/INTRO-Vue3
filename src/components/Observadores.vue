<template>
    <div class="div__obser">
        <input type="text" v-model="name">
        {{ name }}
        <input type="text" v-model="valores">
        {{ valores }}
        <br><br>

        <select v-model="pageCount">
            <option value="5">5</option>
            <option value="10">10</option>
            <option value="15">15</option>
        </select>
        <br>
        {{ pageCount }}
        <br><br>

        <input type="text" v-model="user.first_name">
        <br>
        <input type="text" v-model="user.last_name">
        <br>
        {{ user.first_name }} || {{ user.last_name }}

    </div>
</template>

<script>
export default {
    data() {
        return {
            name: '',
            valores: null,
            pageCount:5,
            user:{
                first_name: '',
                last_name:''
            }
        }
    },

    computed: {

    },

    // Usado para observar uma variável. Crie uma função com o mesmo nome da variável 
    // que o VUe.js entende
    watch: {
        // Na função recebe dois valores: 'new value' e 'old value'
        name() {
            console.log("Estou usando wacth no name")
        },
        valores(newValue, oldValue) {
            this.saveUserNumber(newValue,oldValue)

        },
        pageCount() {
            this.changePage()
        },
        user: {
            handler(){
                console.log('User alterado')
            },
            deep:true
        }
    },

    methods: {
        saveUserNumber(newValue,oldValue) {
            if (newValue >= 5) {
                console.log(oldValue)
            }
        },
        changePage() {
            console.log('Estou de olho no select')
        }
    }

}
</script>

<style>
.div__obser {
    border: 2px solid #ccc;
}
</style>