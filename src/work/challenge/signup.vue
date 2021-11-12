<template>
    <form
        @submit="submit"
        @submit.prevent
    >
        <!--1. สอน form ด้วย ชื่อ -->
        <div class="inputContainer">
            <p>ชื่อ</p>
            <input v-model.trim="name"  />
        </div>
        <!--พาทำ signup -->
        <div class="inputContainer">
            <p>เบอร์โทรศัพท์</p>
            <input v-model.trim="phone"  />
        </div>
        <div class="inputContainer">
            <p>อีเมล</p>
            <input v-model.trim="email"  />
        </div>
        <div class="inputContainer">
            <p>รหัสผ่าน</p>
            <input v-model.trim="password"  />
        </div>
        <div class="inputContainer">
            <p>รหัสผ่านอีกครั้ง</p>
            <p v-show="errorMessage" class="errorMessage">{{ this.errorMessage }}</p>
            <input v-model.trim="confirmPassword" @change="checkPassword" />
        </div>
        <!--2. พาทำ form ตามรูปนี้หน่อย signup -->
        <button type="submit">Submit</button>
    </form>
</template>
<script>
// 1. Define data first
// 2. make Form tag
// 3. inputs ใส่ใน form
// 4. ใส่เพียง 1 submit button
// ให้เห็นว่ามันจะ refesh หน้าก่อน
//  พาเล่น type button type submit
// จะเห็นว่า log ออกพร้อมๆกัน ถ้าไม่ใส่ type อื่นไว้
// 5. validation
// condition ใน submit ถ้าใช้ null จะ check ง่ายกว่า
// ใส่ v show ถ้ามี error message
// validation 2 แบบ alert กับ onchange
export default {
    data() {
        return {
            name: '',
            phone: '',
            email: null,
            password: '',
            confirmPassword: '',
            errorMessage: null,
        }
    },
    methods: {
        showValue: function (data) {
            console.log(data, this[data])
        },
        checkPassword: function () {
            if (this.password != this.confirmPassword) {
                this.errorMessage = 'รหัสผ่านไม่ตรงกัน'
            } else {
                this.errorMessage = null
            }
        },
        submit: function () {
            if ((this.email && this.password && this.confirmPassword) && !this.errorMessage) {
                alert('form submmited')
            } else {
                alert('กรุณากรอก อีเมล, รหัสผ่าน และ รหัสผ่านอีกครั้ง ให้ครบและถูกต้อง')
            }
        }
    }
}
</script>

<style>
.inputContainer {
    margin-bottom: 16px;
    display: flex;
    flex-direction: column;
}
.errorMessage {
    color: red;
}
</style>