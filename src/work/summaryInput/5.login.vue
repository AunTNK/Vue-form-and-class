<template>
    <div>
        <form @submit.prevent="submit">
            <!-- <h1>โจทย์ ลอง ทำ login หน่อย</h1> -->
            <div class="inputContainer">
                <div class="inputTitle">อีเมล</div>
                <input type="email" v-model="email">
            </div>
            <div class="inputContainer">
                <div class="inputTitle">รหัสผ่าน</div>
                <input type="password" v-model.trim="password">
            </div>
            <button type="submit">เข้าสู่ระบบ</button>
        </form>
    </div>
</template>

<script>
export default {
    data() {
        return {
            email: '',
            password: ''
        }
    },
    methods: {
        submit() {
            if (this.email && this.password) {
                alert('เข้าสู่ระบบสำเร็จ')
            } else {
                alert('โปรดกรอกข้อมูลให้ครบถ้วน')
            }
        }
    }
}
</script>

<style>
.inputContainer {
    margin-bottom: 16px;
}
.inputTitle {
    font-size: 1.2rem;
    font-weight: 'bold';
}
</style>