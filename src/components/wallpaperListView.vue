<script setup lang="ts">
import { inject, type Ref } from 'vue'
const bgName = inject('bgName') as Ref<string>
const changeBgNameHandle = (bg: string) => {
  bgName.value = bg
}
</script>

<template>
  <div id="wallpaper-list">
    <ul>
      <li v-for="index in 42" :key="index">
        <img
          @click="changeBgNameHandle(`bg_${index}.png`)"
          :src="`/bg_images/bg_${index}.png`"
        />
      </li>
    </ul>
  </div>
</template>

<style scoped>
#wallpaper-list {
  max-height: 400px;
  overflow: scroll;
}

#wallpaper-list li {
  display: inline-block;
  width: 120px;
  height: 120px;
  margin: 4;
  box-sizing: border-box;
  cursor: pointer;
}

#wallpaper-list li img {
  width: 100%;
  height: 100%;
}
</style>
