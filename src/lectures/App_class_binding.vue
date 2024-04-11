<template>
  <div>
    <div :class="clsObj">텍스트입니다.</div>
    <button @click="toggle">toggle</button>
    <button @click="hasError = !hasError">hasError</button>
  </div>
</template>

<script>
import  {ref} from "vue";
import {computed} from "vue";

export default {
  setup() {
    const isActive = ref(true);
    const hasError = ref(false);
    /*const clsObj = reactive({
      active : isActive,
      'text-danger' : hasError
    })*/

    const clsObj = computed(() => {
      return{
        active : true,
        'text-danger' : true
      }
    })

    const toggle = () => {
      isActive.value = !isActive.value;
    }

    return {isActive, toggle, hasError,clsObj }
  }
}
</script>

<style lang="scss" scoped>
  .active{
    font-weight: 900;
  }

  .text-danger{
    color: red;
  }
</style>