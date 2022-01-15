<template>
  <div class="wrapper">
    <header-common />
    <main>
      <slot />
    </main>
    <my-button />
    <footer-common />
  </div>
</template>

<script>
import HeaderCommon from './HeaderCommon'
import FooterCommon from './FooterCommon'
import { defineAsyncComponent } from 'vue'

export default {
  name: "Layout",
  components: {
    HeaderCommon,
    FooterCommon,
    MyButton: defineAsyncComponent(() => import('host/MyButton'))
  },
  setup() {}
}
</script>

<style scoped>
</style>