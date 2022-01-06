<template>
  <div class="app">
    <!-- <p>
      {{ name }} - {{ age }}
    </p>
    <button @click="changeName('zelda')">change name</button>
    <button @click="changeAge(20)">change age</button> -->
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
    /* const state = reactive({ */
    /* name: 'link', */
    /* age: 25 as string | number */
    /* }) */

    /* return{ ...toRefs(state) } */

    /* const name = ref('link') */
    /* const age = ref<number | string>(25) */

    /* return { name, age } */
    const jobs = ref<Job[]>([
      { title: 'farm worker', location: 'young america', salary: 10000, id: 1 },
      { title: 'farmer', location: 'new zealand', salary: 20000, id: 2 },
      { title: 'doctor', location: 'united states', salary: 30000, id: 3 },
    ])
    return { jobs }
  },
  /* methods: { */
  /* changeName(name: string) { */
  /* this.name = name */
  /* return name */
  /* }, */
  /* changeAge(age: number | string) { */
  /* this.age = age */
  /* return age */
  /* }, */
  /* }, */
})
</script>

<style></style>
