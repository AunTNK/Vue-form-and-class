<template>
    <div>
        <!-- สอน Trim input อองเอาไปปรับใช้ดู -->
        <input v-model.trim="name"  />
        <button @click="showValue">value</button>
        <!-- สอน เอาไปใส่ code เก่า แล้วบอกว่า email มันตัดให้ แต่ password
        มันไม่ตัดให้นะ ถ้าไม่แน่ใจควรลองก่อน-->
    </div>
</template>

<script>
export default {
    data() {
        return {
            name: '',
        }
    },
    methods: {
        showValue: function () {
            console.log(this.name)
        }
    }
}
</script>

<style>

</style>