<template>
  <div class="">
    <NuxtLink to="/characters/page1">Charaters</NuxtLink> |
    <NuxtLink to="/locations/page1">Locations</NuxtLink> |
    <NuxtLink to="/episodes/page1">Episodes</NuxtLink>
    <h1>this is Index page</h1>
    <div class="theme">
      <img
        src="https://images.expothemes.com/rick-and-morty/images/rick-and-morty-windows-theme-1-hd.jpg"
        alt=""
      />
    </div>
  </div>
</template>

<script setup>
import {} from "vue";
</script>

<style lang="less" scoped>
h1 {
  text-align: center;
}
.theme {
  display: flex;
  // text-align: center;
  // align-items: center;
  width: 100%;
}
img {
  margin: 0 auto;
  width: 1200px;
}
</style>