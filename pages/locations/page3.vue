<template>
  <div class="">
    <h1>location page3</h1>
    <div class="container">
      <div class="box" v-for="(item, index) in list" :key="index">
        <span>ID:{{ list[index].id }}</span>
        <br />
        <span>Name:{{ list[index].name }}</span>
        <br />
        <span>Type:{{ list[index].type }}</span>
        <br />
        <span>Dimension:{{ list[index].dimension }}</span>
        <br />
        <span>Residents:{{ list[index].residents.length }}</span>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
const res = await useFetch("https://rickandmortyapi.com/api/location?page=3", {
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