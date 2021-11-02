<template>
  <div class="job-list">
    <ul>
      <li v-for="job in jobs" :key="job.id">
        <h2>{{ job.title }} in {{ job.location }}</h2>
        <div class="salary">
          <p>Rp. {{job.salary}}</p>
        </div>
        <div class="description">
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque ut magna ipsum. Aliquam et urna quis purus ullamcorper molestie id in dui. Maecenas sit amet libero sem. Duis bibendum mauris sit amet ligula fringilla, eget gravida ligula vulputate. Cras dignissim ante ipsum. Vivamus mollis sed metus at bibendum. Integer lacinia libero sed tellus aliquam lobortis. Vestibulum odio turpis, lobortis sit amet fringilla id, maximus ultrices turpis.</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import Job from '@/types/Job'

export default defineComponent({
  props : {
    jobs: {
      required: true,
      type: Array as PropType<Job[]>
    }
  }
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
