<template>
  <div class="app">
    Hi, {{ name }} {{ age }}
    <button @click="changeName('Aqma')">Change name</button>
    <button @click="changeAge(24)">Change age</button>
    <br>
    <p>{{ jobs[0].title }}</p>
    <!-- <p v-for="job in jobs" key="job.id">{{ job.title }} - {{ job.location }} - {{ job.salary }}</p> -->
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from 'vue';
import Job from './types/Job'

export default defineComponent({
  name: 'App',
  components: {},
  setup(){
    // const state = reactive({
    //   name: 'Auliya',
    //   age: 25 as number | string
    // })

    // state.name = 999 // cannot change type
    // state.age = '26'

    // return { ...toRefs(state) }

    // const name = ref('Auliya')
    // const age = ref<number|string>(23)

    // // age.value = 25 --> set value if use ref

    // return { name, age}

    const jobs = ref<Job[]>([
        { title: 'Front End Developer', location: 'Bandung', salary: 3000000, id:'1'},
        { title: 'Back End Developer', location: 'Bandung', salary: 4000000, id:'2'},
        { title: 'UI/UX', location: 'Bandung', salary: 3500000, id:'3'},
        { title: 'Fullstack Developer', location: 'Bandung', salary: 5000000, id:'4'},
        { title: 'QA', location: 'Bandung', salary: 4000000, id:'5'},
      ])

    return {jobs}
  },
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
