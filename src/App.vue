<template>
  <div class="app">
    <h1>Hello Vue!</h1>
    <p>
      {{ name }} - {{ age }}
    </p>
    <button @click="changeName('zelda')">change name</button>
    <button @click="changeAge(20)">change age</button>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'App',
  components: {},
  setup() {
    /* const state = reactive({ */
      /* name: 'link', */
      /* age: 25 as string | number */
    /* }) */

    /* return{ ...toRefs(state) } */

    const name = ref('link')
    const age = ref<number | string>(25)

    return { name, age }
  },
  methods: {
    changeName(name: string) {
      this.name = name
      return name
    },
    changeAge(age: number | string) {
      this.age = age
      return age
    },
  },
})
</script>

<style></style>
