<template>
  <TheHeader
    v-show="showHeader"
  />
  <div v-show="showName">
     Nome : {{ firstName }} <br>
     Sobrenome : {{  lastName }}
  </div>

  <div v-for="(obj, index) in todos"  v-bind:key="obj.id">
    <br>
    Título: {{index}} - {{ obj.title }}

  </div>


  //<img alt="Vue logo" src="./assets/logo.png">
  //<HelloWorld msg="Welcome to Your Vue.js App"/>

  <img class="paisagem"
      src="https://img.freepik.com/vetores-premium/paisagem-do-por-do-sol-na-praia-com-arvores_104785-716.jpg?w=900"
      v-bind:alt="imgAlt"

  >
  <h2 v-bind:class=" {'title': true}">
      Curso Vue 3
  </h2>
  
</template>

<script>
import TheHeader from './components/TheHeader.vue'
//import HelloWorld from './components/HelloWorld.vue'


export default {
  name: 'App',
  components: {
    //HelloWorld, 
    TheHeader
    
  },

  data() {
    return {
      showHeader: true,
      firstName: "John",
      lastName: "Snow",
      showName: true,
      imgAlt : "Foto de Paisagem",

      todos : [
        {
          "userId" : 1,
          "id" : 1,
          "title" : "delectus aut autem",
          "completed" : false
        },
        {
          "userId" : 2,
          "id" : 2,
          "title" : "Bons livros são melhores em papel",
          "completed" : false
        },
        {
          "userId" : 3,
          "id" : 3,
          "title" : "Sempre há uma segunda chace para o amor",
          "completed" : true
        }
      ]
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

.paisagem {
  width: 250px;
}

.title {
  color: blue;
}
</style>
