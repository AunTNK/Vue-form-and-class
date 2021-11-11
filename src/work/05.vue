<template>
    <form
        @submit="submit"
        @submit.prevent
    >
        <!--1. สอน form ด้วย ชื่อ -->
        <div class="inputContainer">
            <p>ชื่อ</p>
            <input v-model.trim="name"  />
            <div>
                <button type="button" @click="showValue('name')">showValue</button>
            </div>
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
// 5. validation alert ไปก่อน
export default {
    data() {
        return {
            name: null,
        }
    },
    methods: {
        showValue: function (data) {
            console.log(data, this[data])
        },
        submit: function () {
            // if (this.todo != '') { ก่อนและค่อยเปลี่ยนเป็น null
            if (!this.name) {
                alert('กรุณากรอกให้ครบทุกช่อง')
            } else {
                alert('form submit')
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
</style>