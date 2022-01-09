<template>
  <div>
    <header>Remote header</header>
    <main>
      Button from host:
      <suspense>
        <my-button />
        <template #fallback>
          Error
        </template>
      </suspense>
    </main>
    <footer>Remote footer</footer>
  </div>
</template>

<script>
import { defineAsyncComponent } from 'vue'

export default {
  name: "Layout",
  components: {
    MyButton: defineAsyncComponent(() => import('host/MyButton'))
  }
}
</script>

<style scoped>

</style>