<template>
    <form
        @submit="submit"
        @submit.prevent
    >
        <!--สอน form ด้วย TODO list -->
        <div class="inputContainer">
            <p>สิ่งที่ต้องทำ</p>
            <input v-model.trim="todo"  />
            <div>
                <button type="submit">Submit</button>
            </div>
        </div>
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
export default {
    data() {
        return {
            todo: null,
        }
    },
    methods: {
        showValue: function (data) {
            console.log(data, this[data])
        },
        submit: function () {
            // if (this.todo != '') { ก่อนและค่อยเปลี่ยนเป็น null
            if (!this.todo) {
                alert('กรุณากรอกให้ครบทุกช่อง')
            } else {
                alert('form submited')
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
}
</style>