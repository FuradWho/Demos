<script setup>
import { ref } from 'vue'
const activeIndex = ref('2');
const handleSelect = () => { }
</script>

<template>
  <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" :ellipsis="false"
    @select="handleSelect">
    <el-menu-item index="0">LOGO</el-menu-item>
    <div class="flex-grow" />
    <el-menu-item index="1">Processing Center</el-menu-item>
  </el-menu>
</template>

<style scoped>
.flex-grow {
  flex-grow: 2;
}
</style>
