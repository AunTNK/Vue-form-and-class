<template>
    <div>
        <input type="text" v-model.trim="name">
        <button @click="submit('name')">Submit</button>
        <div>
            <div>อายุ</div>
            <input type="number" v-model.number="age">
            <button @click="submit('age')">Submit</button>
        </div>
        <div>
            <div>ที่อยู่</div>
            <textarea cols="30" rows="10" v-model.trim="address"></textarea>
            <button @click="submit('address')">Submit</button>
        </div>
        <h1>ให้สร้าง textarea เกี่ยวกับตัวเอง</h1>
        <textarea cols="30" rows="10" v-model.trim="aboutMe"></textarea>
        <button @click="submit('aboutMe')">Submit</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            name: '',
            age: 0,
            address: '',
            aboutMe: ''
        }
    },
    methods: {
        submit(inputName){
            // Input นี้มีค่า เท่าใด
            console.log(inputName,this[inputName])
        }
    }
}
</script>

<style>
html, body {
    padding: 20px;
}
</style>