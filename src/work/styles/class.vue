<template>
    <!-- เปิดปิืด -->
    <!-- <button :class="{activeMenu: currentActiveMenu === 'menu1'}" @click="toggleMenu">menu1</button> -->
    <button :class="{ activeMenu }" @click="toggleMenu">menu1</button>
    <!-- <button :class="{ activeMenu: isActive }" @click="toggleMenu">Menu</button> -->
     <!-- แทนค่า -->
    <!-- <button :class="isActive ? 'activeMenu' : 'deActiveMenu'" @click="toggleMenu">Menu</button> -->
    <!-- <button :class="customClassName" @click="toggleMenu">Menu</button> -->
</template>
<script>
export default {
    data() {
        return {
            activeMenu: false,
            isActive: false,
            currentActiveMenu: 'menu1',
            customClassName: 'activeMenu'
        }
    },
    methods: {
        toggleMenu: function () {
            // if (this.todo != '') { ก่อนและค่อยเปลี่ยนเป็น null
            this.activeMenu = !this.activeMenu
            // this.isActive = !this.isActive
            // this.currentActiveMenu = this.currentActiveMenu === 'menu1' ? '' : 'menu1'
            // this.customClassName = this.customClassName ? null : 'activeMenu'
        }
    }
}
</script>

<style>
.inputContainer {
    margin-bottom: 16px;
}
.errorMessage {
    color: red;
}
.activeMenu {
    background-color: red;
}
.deActiveMenu {
    background-color: gray;
}
</style>