<template>
  <div>
    <p>{{message}}</p>
    <button @click="addMessage">addClick</button>
  </div>
</template>

<script>
import {ref} from "vue";

export default {
  setup() {
    let message = ref('Hello Vue');
    const addMessage = () => {
      message.value += '!';
    }
    return {
      message,
      addMessage,
    }
  }
}
</script>

<style lang="scss" scoped>

</style>