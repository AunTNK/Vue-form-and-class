<template>
    <div>
        <!-- สอน Text input ให้ทำ เบอร์โทรศัพท์ -->
        <input v-model="name" type="text" />
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