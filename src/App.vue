<template>
  <div class="app">
    <JobsList :jobs="jobs" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
import JobsList from './components/JobsList.vue'
import Job from './types/job'

export default defineComponent({
  name: 'App',
  components: {
    JobsList,
  },
  setup() {
    const jobs = ref<Job[]>([
      { title: 'farm worker', location: 'young america', salary: 10000, id: 1 },
      { title: 'farmer', location: 'new zealand', salary: 20000, id: 2 },
      { title: 'doctor', location: 'united states', salary: 30000, id: 3 },
      { title: 'teacher', location: 'united states', salary: 40000, id: 4 },
      { title: 'engineer', location: 'united states', salary: 50000, id: 5 },
    ])
    return { jobs }
  },
})
</script>

<style></style>
