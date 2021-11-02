<template>
  <div class="app">
    <JobList :jobs="jobs"/> 
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from 'vue';
import JobList from './components/JobList.vue'
import Job from './types/Job'

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

    return {jobs}
  },
});
</script>

<style>
</style>
