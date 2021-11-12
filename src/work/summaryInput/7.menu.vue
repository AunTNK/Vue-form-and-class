<template>
    <div>
        <!-- 1. ชื่อคลาส -->
        <h4>ใช้ชื่อคลาส</h4>
        <button :class="customClassName">Menu</button>
        <!-- 2. เงื่อนไข -->
        <h4>เงื่อนไข</h4>
        <button :class="isActive ? 'activeMenu' : 'defaultMenu'" @click="toggle">Menu</button>
        <h4>เปิดปิดคลาสโดยใช้ boolean ตรงๆ</h4>
        <button :class="{ activeMenu: isDisplay }" @click="toggleDisplay">Menu 2</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            customClassName: 'activeMenu',
            isActive: false,
            tab: 1,
            isDisplay: false
        }
    },
    methods: {
        toggle() {
            this.isActive = !this.isActive
        },
        changeTab(tabNumber) {
            this.tab = tabNumber
        },
        toggleDisplay() {
            this.isDisplay = !this.isDisplay
        }
    }
}
</script>

<style>
.activeMenu {
    background-color: crimson;
}
.defaultMenu {
    background-color: gray;
}
</style>