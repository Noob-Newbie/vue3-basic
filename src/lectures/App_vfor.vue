<template>
  <div>
    <ul>
    <!-- 템플릿 방식
    <template v-for="(item,index) in items" :key="item.id">
        <li v-if="item.id % 2 === 0">
          ID : {{item.id}}
          인덱스 : {{index}}
          {{item.message}}
        </li>
      </template>-->

      <li v-for="item in evenItems" :key="item.id">
        ID : {{item.id}}
        인덱스 : {{index}}
        {{item.message}}
      </li>
    </ul>
    <ul>
      <li v-for="(value, key, index) in myObj" :key="key">
        {{index}} - {{key}} - {{value}}
      </li>
    </ul>

  </div>
</template>

<!--
  v-for 에 다수의 요소를 받아 사용하고 싶을경우 중괄호 대괄호가 아닌
  ()일반 괄호를 사용해야 함
-->

<script>
import {computed, reactive} from "vue";

export default {
  setup() {
    const items = reactive([
      {id: 1, message: 'java'},
      {id: 2, message: 'script'},
      {id: 3, message: 'vue'},
      {id: 4, message: 'react'}
    ])

    const evenItems = computed(() => items.filter(item => item.id %2 ===0))

    const myObj = reactive({
      title : '제목',
      author : '홍길동',
      publishedDate: new Date(),
    })
    return {items, evenItems, myObj}
  }
}
</script>

<style lang="scss" scoped>

</style>