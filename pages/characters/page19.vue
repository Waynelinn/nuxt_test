<template>
  <div class="">
    <h1>character page19</h1>
    <div class="container">
      <div calss="box" v-for="(item, index) in list" :key="index">
        <span>ID:{{ list[index].id }}</span>
        <br />
        <span>Name:{{ list[index].name }}</span>
        <br />
        <span>Gender:{{ list[index].gender }}</span>
        <br />
        <span>Species:{{ list[index].species }}</span>
        <br />
        <span>Status:{{ list[index].status }}</span>
        <br />
        <span>Location:{{ list[index].location.name }}</span>
        <!-- <span>url:{{ list[0].location.url }}</span> -->
        <br />
        <img :src="list[index].image" alt="" />
        <br />
        <span>Created:{{ list[index].created }}</span>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
const res = await useFetch(
  "https://rickandmortyapi.com/api/character?page=19",
  {
    method: "GET",
  }
);
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