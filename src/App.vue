<template>
  <div class="app">
    <header>
      <div class="title">
        <h1>Hyrule Jobs</h1>
      </div>
      <div class="order">
        <button @click="handleClick('title')">order by title</button>
        <button @click="handleClick('location')">
          order by location
        </button>
        <button @click="handleClick('salary')">
          order by salary
        </button>
      </div>
    </header>
    <JobsList :jobs="jobs" :order="order" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
import JobsList from './components/JobsList.vue'
import Job from './types/Job'
import OrderTerm from './types/OrderTerm'

export default defineComponent({
  name: 'App',
  components: {
    JobsList,
  },
  setup() {
    const jobs = ref<Job[]>([
      {
        title: 'farm worker',
        location: 'young america',
        salary: 10000,
        id: 1,
      },
      {
        title: 'farmer',
        location: 'new zealand',
        salary: 20000,
        id: 2,
      },
      {
        title: 'doctor',
        location: 'united states',
        salary: 30000,
        id: 3,
      },
      {
        title: 'teacher',
        location: 'united states',
        salary: 40000,
        id: 4,
      },
      {
        title: 'engineer',
        location: 'united states',
        salary: 50000,
        id: 5,
      },
    ])

    const order = ref<OrderTerm>('title')

    const handleClick = (term: OrderTerm) => {
      order.value = term
    }

    return { jobs, handleClick, order }
  },
})
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
  padding: 8px 10px;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
}
header .title {
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
