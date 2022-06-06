<template>
  <div id="app">
    <TestInput v-model='data.id' :label="info.id" />
    <TestInput v-model="data.password" :label="info.pw" />

    <TestBtn @click="handleButton(data)" />
  </div>
</template>

<script>
import TestInput from './components/TestInput.vue'
import TestBtn from "@/components/TestBtn";

export default {
  name: 'App',
  components: {
    TestInput,
    TestBtn,
  },
  data() {
    return {
      data: {
        id: '',
        password: '',
      },
      info: {
        id: 'ID',
        pw: 'Password'
      }
    }

  },
  methods: {
    handleButton(item) {
      console.log("result::",item)
      return item;
    },
  }
}
</script>

<style>
#app {
  width: 300px;
  margin: 0 auto;
  border: 1px solid black;
  padding: 20px;
}
</style>
