<template>
    <div class="h-logo">LOGO</div>
    <div class="h-div"></div>
    <el-menu mode="horizontal" :ellipsis="ellipsis_value">
        <el-menu-item index="0">Processing Center</el-menu-item>
        <el-menu-item index="1">Processing Center</el-menu-item>
        <el-menu-item index="2">Processing Center</el-menu-item>
        <el-menu-item index="3">Processing Center</el-menu-item>
        <el-menu-item index="4">Processing Center</el-menu-item>
    </el-menu>
</template>

<script>
export default {
    data() {
        return {
            ellipsis_value: true
        }
    },

}

</script>

<style scoped>
.el-menu {
    width: 47%;
    margin-left: auto;
}

.h-logo {
    position: relative;
    left: 10px;
    width: 200px;
    background-color: aqua;
}
.h-div{
    flex-grow: 1;
}

.el-menu-item {
    text-align: center;
    width: 150px;
    /* margin-left: 10px; */
}
.el-menu-item.is-active {
  background-color: white !important;
}
</style>