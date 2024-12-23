<template>
  <div>
    <h2>{{ teacher.name }}</h2>
    <h1>강의가 있습니까?</h1>
    <p>{{ hasLecture }}</p>
    <p>{{ fullName }}</p>
  </div>
</template>

<script>
import { computed, reactive, ref } from 'vue'

export default {
  setup() {
    const teacher = reactive({
      name: '짐코딩',
      lectures: ['HTML/CSS', 'Javascript', 'Vue3'],
    })
    const hasLecture = computed(() => {
      return teacher.lectures.length > 0 ? '있음 😁' : '없음' //함수도 이렇게 가능하지만 캐시가 적어 효율?적이다
    })
    const firstName = ref('홍')
    const lastName = ref('길동')
    // const fullName = computed(() => firstName.value + ' ' + lastName.value)
    const fullName = computed({
      get() {
        return firstName.value + ' ' + lastName.value
      },
      set(value) {
        // console.log('value', value);
        ;[firstName.value, lastName.value] = value.split('')
      },
    })
    fullName.value = '이규성'
    return {
      teacher,
      hasLecture,
      fullName,
      firstName,
      lastName,
    }
  },
}
</script>

<style lang="scss" scoped></style>
