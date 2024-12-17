<template>
  <div>
    <p>
      {{ counter }}
    </p>
    <p>
      {{ msg }}
    </p>
    <button @click="increment">click</button>
  </div>
</template>

<script>
import { ref } from 'vue'
export default {
  setup() {
    const counter = ref(0)
    const msg = ref('Hello Vue')
    const increment = () => {
      counter.value++
    }
    return {
      counter,
      msg,
      increment,
    }
  },
}
</script>

<style lang="scss" scoped></style>
