<template>
  <button v-on:click="incrememt">click me!! {{ state.count }}</button>
</template>

<script>
import { reactive } from 'vue'

export default {
  setup() {
    const state = reactive({
      count: 0,
      deep: {
        count: 0,
      },
    })
    const incrememt = () => {
      state.count++
      state.deep.count++
    }
    return {
      state,
      incrememt,
    }
  },
}
</script>

<style lang="scss" scoped></style>
