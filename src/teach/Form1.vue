<template>
    <div>
        <h1>สร้าง project ใหม่ ทำ form todo </h1>
         <h4>ใส่ input สิ่งที่ต้องทำเข้ามา required  </h4>
        <form @submit.prevent="submit">
            <!-- <h4>1. inpus อยู่ใต้ form</h4>
            <h4>2. มี 1 submit button</h4> -->
            <div>
                <div>email</div>
                <input type="email" v-model="email" required>
                 <button type="button" @click="logData('email')">log</button>
            </div>
            <button type="submit">Submit</button>
        </form>
    </div>
</template>

<script>
export default {
    data() {
        return {
            email: ''
        }
    },
    methods: {
        submit() {
            alert('Success')
        },
        logData(inputName){
            // Input นี้มีค่า เท่าใด
            console.log(inputName,this[inputName])
        }
    }
}
</script>

<style>

</style>