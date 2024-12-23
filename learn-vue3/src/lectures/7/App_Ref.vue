<template>
  <div>
    <p>{{ message }}</p>
    <button v-on:click="addMsg">클릭!</button>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  setup() {
    let message = ref('Hello Vue!!')
    const addMsg = () => {
      message.value = message.value + '!?'
    }

    return {
      message,
      addMsg,
    }
  },
}
</script>

<style lang="scss" scoped></style>
