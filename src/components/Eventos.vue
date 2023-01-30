<template>
    <div class="div__events" >
        <button @click="onClick">
            Enviar
        </button>
        <div 
        @mouseover="onMouseOver"
        @mouseout="onMouseOut"
        
        >
            Passei o mouse por cima 
        </div>
        <input type="text" @keyup.enter="onKeyUp">
        
    </div>
    <!--  modificadors de eventos -->
    <!-- .prevent ; .stop; .capture; .self; .once; .passive -->
</template>

<script>
export default {
    data() {
        return {
            // $e = evento
            // As funções estão sendo utilizadas sem os () para que o $e seja passado para 
            // dentro dos métodos.
            onClick($e) {
                console.log('click',$e)
            },
            onMouseOver($e) {
                console.log('Passei o mouse por cima',$e)
            },
            onMouseOut($e) {
                console.log('Passei e tirei o mouse por cima',$e)
            },
            onKeyUp($e) {
                console.log('Foi digitado algo e só foi finalizado a ação depois do enter', $e)
            }
        } 
    }
}
</script>

<style>
    .div__events{
        border: 2px solid blue;
    }
</style>