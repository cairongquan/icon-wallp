<script setup lang="ts">
import { computed, inject, type Ref } from 'vue'
import materialIcons from 'material-icons/_data/versions.json'

import 'material-icons/iconfont/material-icons.css'

const renderMaterialList = computed<string[]>(() => {
  return Object.keys(materialIcons)
})
const iconList = inject('iconList') as Ref<string[]>
const selectIconHandle = (iconName: string) => {
  iconList.value.includes(iconName)
    ? iconList.value.splice(iconList.value.indexOf(iconName), 1)
    : iconList.value.push(iconName)
}
</script>

<template>
  <div id="icon-list-view">
    <ul>
      <li
        @click="selectIconHandle(icon)"
        v-for="icon in renderMaterialList"
        :key="icon"
      >
        <span class="material-icons">{{ icon }}</span>
      </li>
    </ul>
  </div>
</template>

<style scoped>
#icon-list-view {
  max-height: 300px;
  overflow: scroll;
  padding: 20px;
}

#icon-list-view li {
  font-size: 26px;
  width: 20px;
  height: 20px;
  line-height: 10px;
  text-align: center;
  display: inline-block;
  text-align: center;
  user-select: none;
  padding: 12px;
  transition: all ease 220ms;
  cursor: pointer;
}

#icon-list-view li:hover {
  background-color: rgba(255, 255, 255 255, 0.67);
  box-shadow: 1px 1px 12px 12px rgba(0, 0, 0, 0.1);
  border-radius: 2px;
}
</style>
