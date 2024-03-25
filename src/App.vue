<!--
 * @Author: cairq cairq@tongbaninfo.com
 * @Date: 2024-03-24 10:43:09
 * @LastEditors: 蔡荣诠 cairq@tongbaninfo.com
 * @LastEditTime: 2024-03-25 16:42:21
 * @FilePath: \icon-wallp\src\App.vue
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
<script setup>
import { reactive, provide, toRef } from 'vue'
import IconListView from './components/IconListView.vue'
import WallpaperListView from './components/wallpaperListView.vue'
import RightContent from './components/rightContent.vue'

const option = reactive({ iconList: [], bgName: '' })
provide('iconList', toRef(option, 'iconList'))
provide('bgName', toRef(option, 'bgName'))
</script>

<template>
  <div id="app">
    <div class="app-left-menu">
      <el-collapse>
        <el-collapse-item title="GoogleIcon" name="1">
          <icon-list-view></icon-list-view>
        </el-collapse-item>
        <el-collapse-item title="Wallpaper" name="2">
          <wallpaper-list-view></wallpaper-list-view>
        </el-collapse-item>
      </el-collapse>
    </div>
    <div class="app-right-content">
      <right-content></right-content>
    </div>
  </div>
</template>
