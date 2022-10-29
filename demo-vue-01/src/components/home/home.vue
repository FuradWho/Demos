<template>
    <div class="common-layout">
        <el-header>
            <div class="h-logo">LOGO</div>
            <div class="h-div"></div>
            <el-menu mode="horizontal" :ellipsis="ellipsis_value" :default-active="activeIndex">
                <el-menu-item index="0" @click="goAnchor('0')">Processing Center</el-menu-item>
                <el-menu-item index="1" @click="goAnchor('1')">Processing Center</el-menu-item>
                <el-menu-item index="2" @click="goAnchor('2')">Processing Center</el-menu-item>
                <el-menu-item index="3" @click="goAnchor('3')">Processing Center</el-menu-item>
                <el-menu-item index="4" @click="goAnchor('4')">Processing Center</el-menu-item>
            </el-menu>
        </el-header>
        <el-main @scroll="onScroll">
            <div class="content">
                <div id="0">
                    content-0
                </div>
                <div id="1">
                    content-1
                </div>
                <div id="2">
                    content-2
                </div>
                <div id="3">
                    content-3
                </div>
                <div id="4">
                    content-4
                </div>
            </div>
        </el-main>
        <el-footer>Footer</el-footer>
    </div>
</template>

<script>
export default {
    data() {
        return {
            ellipsis_value: true,
            activeIndex: "1",
        }
    },
    mounted() {
        window.addEventListener('scroll', this.onScroll)
    },
    destroy() {
        window.removeEventListener('scroll', this.onScroll)
    },
    methods: {
        onScroll() {
            const navContents = document.querySelectorAll('.content div')
            const offsetTopArr = []
            navContents.forEach(item => {
                offsetTopArr.push(item.offsetTop)
            })
            const scrollTop = document.documentElement.scrollTop || document.body.scrollTop
            let navIndex = 0
            for (let n = 0; n < offsetTopArr.length; n++) {
                if (scrollTop >= offsetTopArr[n]) {
                    navIndex = n
                }
            }
            this.activeIndex = navIndex
        },
        goAnchor(id) {
            var anchor = document.getElementById(id);
            anchor.scrollIntoView();
        },
    }

}
</script>

<style  scoped lang="scss">
.content div {
    width: 100%;
    height: 800px;
    font-size: 36px;
    padding: 20px;
    background-color: #7ec384;
}

.common-layout {

    .el-header,
    .el-footer,
    // .el-main,
    .el-aside {
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .el-footer {
        background-color: var(--el-color-primary-light-7);
        color: var(--el-text-color-primary);
        text-align: center;
    }

    .el-header {
        // position: fixed;
        text-align: center;
        width: 100%;
        --el-header-padding: 0 0px;
        z-index: 1000;
        background-color: white;
    }

    .el-aside {
        background-color: var(--el-color-primary-light-8);
        color: var(--el-text-color-primary);
        text-align: center;
    }

    .el-main {
        display: flex;
        // justify-content: center;
        background-color: var(--el-color-primary-light-9);
        color: var(--el-text-color-primary);
        // text-align: center;
        // height: 1500px;
        height: 4220px;
        overflow-y: auto;
    }
}

.header {
    width: 100%;
}

.el-menu {
    width: 48%;
    margin-left: auto;
}

.h-logo {
    position: relative;
    left: 10px;
    width: 170px;
    background-color: aqua;
}

.h-div {
    flex-grow: 1;
}

.el-menu-item {
    text-align: center;
    width: 150px;
    /* margin-left: 10px; */
}
</style>
