<template>
  <div id="app">
    <h2>Todos: v-for Range 예제</h2>
    <span
      v-for="(item,i) in 10"
      :key="i"
    >{{ item }} - {{ i }}<br></span>

    <h1>여행지 리스트</h1>

    <ul>
      <li
        v-for="value in array"
        :key="value.id"
      >
        {{ value }}
      </li>
    </ul>
    <v-btn @click="shift">
      첫번째 요소 제거
    </v-btn>
  </div>
</template>

<script>
export default {
  el: '#app',
  data: () => ({
    array: [1, 2, 3, 4]
  }),
  methods: {
    shift() {
      this.array.shift();
    }
  }
}
</script>

<style scoped>

</style>