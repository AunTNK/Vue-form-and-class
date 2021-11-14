<template>
    <div>
        <!-- ชื่อ
        เบอร์โทร
        อีเมล
        รหัสผ่าน
        รหัสผ่านอีกครั้ง -->
        h
        <form @submit.prevent="submit">
            <div class="inputContainer">
                <div class="inputTitle">ชื่อ</div>
                <input type="text" v-model.trim="name" required>
            </div>
            <div class="inputContainer">
                <div class="inputTitle">เบอร์โทรศัพท์</div>
                <input type="text" v-model.trim="phone" required>
            </div>
            <div class="inputContainer">
                <div class="inputTitle">อีเมล</div>
                <input type="email" v-model="email" required>
            </div>
            <div class="inputContainer">
                <div class="inputTitle">รหัสผ่าน</div>
                <input type="password" v-model.trim="password" @change="handlePasswordChange" required>
                <p v-show="isPasswordError" class="errorMessage">รหัสผ่านต้องเท่ากับรหัสผ่านอีกครั้ง</p>
            </div>
            <div class="inputContainer">
                <div class="inputTitle">รหัสผ่านอีกครั้ง</div>
                <input type="password" v-model.trim="confirmPassword" @change="handlePasswordChange" required>
                <p v-show="isPasswordError" class="errorMessage">รหัสผ่านต้องเท่ากับรหัสผ่านอีกครั้ง</p>
            </div>
            <button type="submit">สมัครสมาชิก</button>
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
            confirmPassword: '',
            isPasswordError: false
        }
    },
    methods: {
        submit() {
            if (this.password === this.confirmPassword) {
                console.log('name', this.name)
                alert('สมัครสมาชิกสำเร็จ')
            } else {
                alert('กรุณาตรวจสอบรหัสผ่าน')
            }
        },
        handlePasswordChange() {
            if (this.password !== this.confirmPassword) {
                this.isPasswordError = true
            } else {
                this.isPasswordError = false
            }
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
    font-size: 0.5rem;
}
</style>