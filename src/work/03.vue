<template>
    <div>
        <!-- สอน Number input ให้ทำจำนวนพี่น้อง สอนใช้ .number-->
        <input v-model.number="age"  type="number" />
        <button @click="showValue">value</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            age: 0,
        }
    },
    methods: {
        showValue: function () {
            console.log(this.age)
        }
    }
}
</script>

<style>

</style>