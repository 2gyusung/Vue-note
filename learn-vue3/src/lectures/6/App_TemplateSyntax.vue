<template>
  <div>
    <h2>보간법</h2>
    <p>
      {{ message }}
    </p>
    <p v-once>
      {{ message }}
    </p>
    <button v-on:click="message = message + '!'">Click!!</button>
    <hr />
    <h2>v-html</h2>
    <p v-html="rowHtml"></p>
    <hr />
    <h2 v-bind:title="dTitle">속성 바인디</h2>
    <input type="text" value="홍길동" v-bind:disabled="IsInputDis" />
    <input v-bind="attrs" />
    <h2>Javascript</h2>
    {{ message.split('').reverse().join('') }} <br />
    {{ IsInputDis ? '예' : '아니여' }}
  </div>
</template>

<script>
import { ref } from 'vue'
export default {
  setup() {
    const message = ref('안녕하세요')
    const rowHtml = ref('<strong>안녕하세요</strong>')
    const dTitle = ref('안녕하세요!!')
    const IsInputDis = ref(false)
    const attrs = ref({
      type: 'password',
      value: '1234',
      disabled: false,
    })
    return {
      message,
      rowHtml,
      dTitle,
      IsInputDis,
      attrs,
    }
  },
}
</script>

<style lang="scss" scoped></style>
