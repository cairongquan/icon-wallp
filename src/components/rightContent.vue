<!--
 * @Author: 蔡荣诠 cairq@tongbaninfo.com
 * @Date: 2024-03-25 16:22:51
 * @LastEditors: 蔡荣诠 cairq@tongbaninfo.com
 * @LastEditTime: 2024-03-25 20:41:51
 * @FilePath: /icon-wallp/src/components/rightContent.vue
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
<script setup lang="ts">
import { inject } from 'vue'

const iconList = inject('iconList')
const bgName = inject('bgName')
</script>

<template>
  <div id="right-content">
    {{ iconList }}
    {{ bgName }}
  </div>
</template>
