<template>
    <!-- if else หรือ pure focus -->
    <div>
        <button :class="currentActiveMenu === 'อาหาร' ? 'activeMenu' : 'menu'" @click="active('อาหาร')" autofocus>อาหาร</button>
        <button :class="currentActiveMenu === 'สมาชิก' ? 'activeMenu' : 'menu'" @click="active('สมาชิก')">สมาชิก</button>
        <button :class="currentActiveMenu === 'รายการสั่งซื้อ' ? 'activeMenu' : 'menu'" @click="active('รายการสั่งซื้อ')">รายการสั่งซื้อ</button>
    </div>
</template>
<script>
export default {
    data() {
        return {
            currentActiveMenu: 'อาหาร',
        }
    },
    methods: {
        active: function (menu) {
            this.currentActiveMenu = menu
        }
    }
}
</script>

<style>
button {
    width: 100px;
    height: 40px;
    margin-right: 16px;
    border-radius: 20px;
    border: none;
    background-color: #eeeeee;
}
.activeMenu {
    background-color: #9a0606;
    color: white;
}

/* สามารถใช้ได้แต่ ยังไงก็ควรเก็บไว้ ให้รู้ว่าตอนนี้อยู่ tab ไหนใช้ content แบบไหน
/* และจะมีปัญหาถ้าไม่ใช่แถบแรกแล้ว autofocus เก็บไว้ ดีกว่า ไม่งั้นต้องใช้ ref จะยาก
/* button:focus {
    background-color: #9a0606;
    color: white;
} */
</style>