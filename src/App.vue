<template>
  <div class="app">
    <header>
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
</style>
