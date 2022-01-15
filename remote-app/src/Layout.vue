<template>
  <div class="wrapper">
    <header-common />
    <main>
      <slot />
    </main>
    <button @click="handleClickButton">Click me</button>
    My counter {{ counter }}
    <footer-common />
  </div>
</template>

<script>
import HeaderCommon from './HeaderCommon'
import FooterCommon from './FooterCommon'
import { reactive, toRefs } from 'vue'

export default {
  name: "Layout",
  components: {
    HeaderCommon,
    FooterCommon,
  },
  setup() {
    const data = reactive({
      counter: 0
    })

    const handleClickButton = () => {
      data.counter++
    }

    return {
      ...toRefs(data),

      handleClickButton
    }
  }
}
</script>

<style scoped>
</style>