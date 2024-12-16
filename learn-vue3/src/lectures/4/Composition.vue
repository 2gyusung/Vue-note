<template>
  <div>
    <h2>반응형 메세지</h2>
    <p>{{ reactiveMessage }}</p>
    <button v-on:click="addMsg">ADD</button>
    <h2>일반 메세지</h2>
    <p>{{ normalMessage }}</p>
    <button v-on:click="addNoMsg">ADD</button>
  </div>
</template>

<script>
import { ref } from 'vue'
export default {
  setup() {
    const reactiveMessage = ref('Hello')
    const addMsg = () => {
      reactiveMessage.value = reactiveMessage.value + '!'
    }
    const normalMessage = ref('MNHello')
    const addNoMsg = () => {
      reactiveMessage.value = reactiveMessage.value + '!'
    }
    return {
      reactiveMessage,
      normalMessage,
      addMsg,
      addNoMsg,
    }
  },
}
</script>

<style lang="scss" scoped></style>
