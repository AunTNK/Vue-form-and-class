 <!-- น่าจะไม่ทันให้ไปทำเป็น home work ดีกว่ามั้ง -->
 <template>
    <form
        @submit="login"
        @submit.prevent
    >
        <div class="inputContainer">
            <p>อีเมล</p>
            <input v-model.trim="email"  />
        </div>
         <div class="inputContainer">
            <p>รหัสผ่าน</p>
            <input v-model.trim="password"  />
        </div>
        <button type="login">เข้าสู่ระบบ</button>
    </form>
</template>
<script>
export default {
    data() {
        return {
            email: null,
            password: '',
        }
    },
    methods: {
        showValue: function (data) {
            console.log(data, this[data])
        },
        login: function () {
            if (this.email === 'admin' && this.password === 'password') {
                alert('logged in')
            } else if (!this.email && !this.password){
                alert('กรุณากรอกอีเมล และรหัสผ่าน')
            } else {
                 alert('อีเมลหรือรหัสผ่านไม่ถูกต้อง กรุณาลองอีกครั้ง')
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