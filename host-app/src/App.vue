<template>
  <suspense>
    <Layout>
      <div class="host-title">
        Hello from remote slot in host app
      </div>
    </Layout>
    <template #fallback>
      <div class="danger-message">
        Remote die :(
      </div>
    </template>
  </suspense>
</template>

<script>
import MyButton from './components/MyButton.vue'
import {defineAsyncComponent} from "vue";

export default {
  name: 'App',
  components: {
    MyButton,
    Layout: defineAsyncComponent(() => import('layout/Layout')),
  },
  setup() {}
}
</script>

<style scoped>
.host-title {
  font-size: 30px;
  color: green;
  font-weight: bold;
}

.danger-message {
  color: red;
  font-weight: bold;
  font-size: 40px;
}
</style>