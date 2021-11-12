<template>
    <div>
        <!-- <h1>โจทย์ ลอง ทำ signup หน่อย</h1> -->
        <form @submit.prevent="submit">
            <div class="inputContainer">
                <div>ชื่อ</div>
                <input type="text" v-model.trim="name">
            </div>
            <div class="inputContainer">
                <div>เบอร์โทรศัพท์</div>
                <input type="text" v-model.trim="phone">
            </div>
            <div class="inputContainer">
                <div>อีเมล</div>
                <input type="email" v-model="email">
            </div>
            <!-- ผมยังไม่ได้สอน validate ตรงนี้ ใช้ if else alert ก่อนได้ครั้ง -->
            <div class="inputContainer">
                <div>รหัสผ่าน</div>
                <input type="password" v-model="password" required>
            </div>
            <div class="inputContainer">
                <div>รหัสผ่านอีกครั้ง</div>
                <input type="password" v-model="confirmPassword" required>
            </div>
            <button class="submitButton" type="submit">Submit</button>
        </form>
    </div>
</template>

<script>
export default {
    data() {
        return {
            name: '',
            phone: '',
            email: '',
            password: '',
            confirmPassword: ''
        }
    },
    methods: {
        submit() {
            // แบบ ง่าย
            if(this.password != this.confirmPassword) {
                alert('Password ต้องเหมือนกับ confirmPassword')
            } else {
                alert('success')
            }
        }
    }
}
</script>

<style>

</style>