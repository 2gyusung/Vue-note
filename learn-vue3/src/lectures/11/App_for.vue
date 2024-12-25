<template>
  <div>
    <ul>
      <template v-for="(item, idx) in items" :key="item.id">
        <!-- <li v-if="item.id % 2 == 0">ID : {{ item.id }} 인덱스 : {{ idx }}, {{ item.msg }}</li> -->
        <li>>ID : {{ item.id }} 인덱스 : {{ idx }}, {{ item.msg }}</li>
      </template>
      <!-- <li v-for="(item, idx) in items" :key="item.id">인덱스 : {{ idx }},{{ item.msg }}</li> -->
      <!-- <li v-for="(item, idx) in items" :key="item.id">인덱스 : {{ idx }},{{ item.msg }}</li> -->
    </ul>
    <hr />
    <ul>
      <li v-for="(value, key, idx) in myObj" :key="key">{{ idx }}, {{ key }} , {{ value }}</li>
    </ul>
  </div>
</template>

<script>
import { computed, reactive } from 'vue'

export default {
  setup() {
    const items = reactive([
      { id: 1, msg: 'Java' },
      { id: 2, msg: 'JavaScript' },
      { id: 3, msg: 'Vue' },
      { id: 4, msg: 'HTML' },
    ])
    const evenItems = computed(() => items.filter(item => item.id % 2 === 0))
    const myObj = reactive({
      title: '제목',
      author: '홍길동',
      publishedat: '2016-01-01',
    })
    return {
      items,
      evenItems,
      myObj,
    }
  },
}
</script>

<style lang="scss" scoped></style>
