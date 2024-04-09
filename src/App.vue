<template>
  <div>
    <h2>{{teacher.name}}</h2>
    <h3>강의가 있습니까?</h3>
    <p>{{hasLecture}}</p>
    <p>{{hasLecture}}</p>
    <p>{{existLecture()}}</p>
    <p>{{existLecture()}}</p>
    <button @click="count++">Counter : {{count}}</button>
    <h2>이름</h2>
    <p>{{fullNm}}</p>
  </div>
</template>

<script>
import {computed, reactive, ref} from "vue";

export default {
  setup() {
    const teacher = reactive({
      name : '테스트',
      lectures : [
          'HTML/CSS',
          'JavaScript',
          'Vue3'
      ]
    })

    //성능적으로 함수보다 computed사용이 좋음
    const hasLecture = computed(() => {
      console.log('computed')
      return teacher.lectures.length > 0 ? '있음' : '없음'
    })

    const existLecture = () => {
      console.log('method')
      return teacher.lectures.length > 0 ? '있음' : '없음'
    }

    const count = ref(0)


    const fNm = ref('길동')
    const lNm = ref('홍')

    const fullNm = computed({
      get() {
        return fNm.value + lNm.value
      },
      set(value){
        console.log(value)
      }

    })

    console.log('콘솔 출력' , fullNm.value);

    return {
      teacher,
      hasLecture,
      existLecture,
      count,
      fullNm
    }
  }
}
</script>

<style lang="scss" scoped>

</style>