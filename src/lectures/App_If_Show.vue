<template>
  <div>
    <h2 v-if="visible">Hello World</h2>
    <h2 v-else>false 입니다</h2>
    <button @click="visible = !visible">toggle</button>
  </div>
  <div>
    <button @click="type = 'A'">A 버튼</button>
    <button @click="type = 'B'">B 버튼</button>
    <button @click="type = 'C'">C 버튼</button>
    <button @click="type = 'D'">D 버튼</button>
    <h2 v-if="type === 'A'">A입니다</h2>
    <h2 v-else-if="type==='B'" >B입니다</h2>
    <h2 v-else-if="type==='C'" >C입니다</h2>
    <h2 v-else>ABC가 아닙니다</h2>
  </div>
  <div>
    <template v-if="visible">
      <h1>Title</h1>
      <p>Paragraph 1</p>
      <p>Paragraph 2</p>
    </template>
    <hr/>
    <h1 v-show="ok">Title 입니다</h1>
    <button @click="ok = !ok">show toggle</button>
  </div>
</template>

<!--
  초기화면 진입 시
  v-if는 실제로 렌더링을 하며
  v-show는 무조건적으로 그려주고 스타일속성에 display속성을 변경해주는 부분이다

  자주 변경될 필요가 있는 요소에 대해서는 show를 사용하는 편이 좋다
-->

<script>
import {ref} from "vue";

export default {
  setup() {

    const visible = ref(true);
    const type = ref('A')
    const ok = ref(true)

    return {visible, type, ok}
  }
}
</script>

<style lang="scss" scoped>

</style>