<template>
  <div class="">
    <h1>Episodes page1</h1>
    <div class="container">
      <div v-for="(item, index) in list" :key="index">
        <span>ID:{{ list[index].id }}</span>
        <br />
        <span>Episode:{{ list[index].episode }}</span>
        <br />
        <span>Name:{{ list[index].name }}</span>
        <br />
        <span>Characters:{{ list[index].characters.length }}</span>
        <br />
        <span>Air_date:{{ list[index].air_date }}</span>
        <br />
        <span>Created:{{ list[index].created }}</span>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
const res = await useFetch("https://rickandmortyapi.com/api/episode", {
  method: "GET",
});
const list = ref(res.data._rawValue.results);
console.log(res);
</script>

<style lang="less" scoped>
h1 {
  text-align: center;
}
.container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  div {
    margin: 10px;
    width: 320px;
    border: 1px solid #ccc;
  }
}
</style>