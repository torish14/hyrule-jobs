<template>
  <div class="app">
    <h1>Hello Vue!</h1>
    <p>
      {{ name }}
    </p>
    <button @click="changeName('zelda')">change name</button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'App',
  components: {},
  data() {
    return {
      name: 'link',
      age: 25 as number | string,
    }
  },
  methods: {
    changeName(name: string) {
      this.name = name
    },
    changeAge(age: number) {
      this.age = age
    },
  },
})
</script>

<style></style>
