<template>
  <div class="app">
    <header>
      <div class="title">
        <img src="./assets/logo.png" alt="site logo" height="50" style="margin-top: 35px;">
        <h1>Hyrule Jobs</h1>
      </div>
      <div class="order">
        <button @click="handleClick('title')">Order By Title</button>
        <button @click="handleClick('location')">Order By Location</button>
        <button @click="handleClick('salary')">Order By Salary</button>
      </div>
    </header>
   
    <JobList :jobs="jobs" :order="order"/> 
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from 'vue';
import JobList from './components/JobList.vue'
import Job from './types/Job'
import OrderTerm from './types/OrderTerm'

export default defineComponent({
  name: 'App',
  components: { JobList },
  setup(){
    const jobs = ref<Job[]>([
        { title: 'Front End Developer', location: 'Bandung', salary: 3000000, id:'1'},
        { title: 'Back End Developer', location: 'Bandung', salary: 4000000, id:'2'},
        { title: 'UI/UX', location: 'Bandung', salary: 3500000, id:'3'},
        { title: 'Fullstack Developer', location: 'Bandung', salary: 5000000, id:'4'},
        { title: 'QA', location: 'Bandung', salary: 4000000, id:'5'},
      ])
    const order = ref<OrderTerm>('title')

    const handleClick = (term: OrderTerm) => {
      order.value = term
    }

    return { jobs, handleClick, order }
  },

});
</script>

<style>
  header {
    text-align: center;
  }
  header .order {
    margin-top: 20px;
  }
  button {
    margin: 0 10px;
    color: #1195c9;
    border: 3px solid #1195c9;
    background: #d5f0ff;
    padding: 8px 16px;
    border-radius: 4px;
    cursor: pointer;
    font-weight: bold;
  }
  header .title{
    display: flex;
    justify-content: center;
  }
  header img {
    width: 60px;
    margin-right: 20px;
  }
  header h1 {
    font-size: 3em;
  }
</style>
