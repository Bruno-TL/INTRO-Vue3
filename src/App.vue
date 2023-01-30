<template>
  <Header v-if="showHeader"/>
  <CheckBox/>
  <Eventos/>
  <PropsComputed/>
  <Observadores/>

  <div v-show="showName">
    Nome: {{ firstName }} <br>
    Sobrenome: {{ lastName }}
  </div>

  <div v-if="accessLevel === 'admin'" >Usuário Admin</div>
  <div v-else-if="accessLevel === 'marketing'">Usuário Marketing</div>
  <div v-else>Usuário normal</div>


  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  
  
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header.vue'
import CheckBox from './components/CheckBox.vue'
import Eventos from './components/Eventos.vue'
import PropsComputed from './components/PropsComputed'
import Observadores from './components/Observadores.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Header,
    CheckBox,
    Eventos,
    PropsComputed,
    Observadores
},
  data() {
    return {
      showHeader: true,
      firstName: 'Thommy',
      lastName: 'Shelby',
      showName: true,
      accessLevel: 'marketing',
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
