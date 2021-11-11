<template>
    <div>
        <!-- สอน Trim input อองเอาไปปรับใช้ดู -->
        <input v-model.trim="name"  />
        <button @click="showValue">value</button>
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