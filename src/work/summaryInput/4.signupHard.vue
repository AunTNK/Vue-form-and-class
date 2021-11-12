<template>
    <div>
        <!-- <h1>โจทย์ ลอง ทำ signup หน่อย</h1> -->
        <form @submit.prevent="submit">
            <div class="inputContainer">
                <div>ชื่อ</div>
                <input type="text" v-model.trim="name" required>
            </div>
            <div class="inputContainer">
                <div>เบอร์โทรศัพท์</div>
                <input type="text" v-model.trim="phone" required>
            </div>
            <div class="inputContainer" required>
                <div>อีเมล</div>
                <input type="email" v-model="email" required>
            </div>
            <!-- ผมยังไม่ได้สอน validate ตรงนี้ ใช้ if else alert ก่อนได้ครั้ง -->
            <div class="inputContainer">
                <div>รหัสผ่าน</div>
                <input type="password" v-model="password" @change="handleOnPassWordChange" required>
                <p v-show="passwordError" class="errorMessage">โปรดตรวจสอบรหัสผ่านและรหัสผ่านอีกครั้ง</p>
            </div>
            <div class="inputContainer">
                <div>รหัสผ่านอีกครั้ง</div>
                <input type="password" v-model="confirmPassword" @change="handleOnPassWordChange" required>
                <p v-show="passwordError" class="errorMessage">โปรดตรวจสอบรหัสผ่านและรหัสผ่านอีกครั้ง</p>
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
            confirmPassword: '',
            passwordError: false,
        }
    },
    methods: {
        handleOnPassWordChange() {
            if ((this.password && this.confirmPassword) && (this.password != this.confirmPassword)) {
                this.passwordError = true
            } else {
                this.passwordError = false
            }
        },
        submit() {
            // แบบ ง่าย
            if (!this.password || this.confirmPassword) {
                alert('กรุณากรอก รหัสผ่าน และ รหัสผ่านอีกครั้ง')
            }
            // else if(this.password != this.confirmPassword) {
            //     alert('Password ต้องเหมือนกับ confirmPassword')
            // }
            else {
                alert('success')
            }
        }
    }
}
</script>

<style>
.errorMessage {
    color: red;
    margin-top: 4px;
}
</style>