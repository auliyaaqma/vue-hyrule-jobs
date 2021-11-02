<template>
  <div class="app">
    Hi, {{ name }} {{ age }}
    <button @click="changeName('Aqma')"> Change name</button>
    <button @click="changeAge(24)"> Change age</button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'App',
  components: {},
  data() {
    return {
      name : 'Auliya',
      age : 23 as number | string
    }
  },
  methods : {
    changeName(name:string){
      this.name = name

      return name
    },
    changeAge(age:number | string){
      this.age = age

      return age
    }
  }
});
</script>

<style>
/*#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}*/
</style>
