<template>
  <div></div>
</template>

<script>
import { reactive, ref } from 'vue'

export default {
  setup() {
    // ref - > 객체
    const count = ref(0)
    const state = reactive({
      count,
    })
    // console.log('state', state.count.value)
    // ref > array
    const msg = ref('hello')
    const arr = reactive(msg)
    console.log('msg', arr[0])
    return {}
  },
}
</script>

<style lang="scss" scoped></style>
