<template>
    <div>
        <h1>Inputs</h1>
        <!-- สอน All form input -->
        <div class="inputContainer">
            <p>ชื่อ</p>
            <input v-model.trim="name"  />
            <button @click="showValue('name')">showValue</button>
        </div>
        <div class="inputContainer">
            <p>อายุ</p>
            <input v-model.number="age" type="number" />
            <button @click="showValue('age')">showValue</button>
        </div>
        <!-- สอน และให้ทำ เกี่ยวกับตัวฉัน -->
        <div class="inputContainer">
            <p>ที่อยู่</p>
            <textarea v-model.trim="address" />
            <button @click="showValue('address')">showValue</button>
        </div>
        <!-- สอน และให้ทำ checkbox มีกิจการส่วนตัว หรือ ได้รับวัคซีนครบแล้ว -->
        <div class="inputContainer">
            <input v-model="isMarriaged" type="checkbox" />
            <label>แต่งงานรึยัง</label>
            <button @click="showValue('isMarriaged')">showValue</button>
        </div>
        <!-- สอน และให้ทำ radio สัตว์เลี้ยงที่ชอบ -->
        <div class="inputContainer">
            <input v-model="gender" type="radio" value="ชาย"/>
            <label>ชาย</label>
             <input v-model="gender" type="radio" value="หญิง"/>
            <label>หญิง</label>
            <button @click="showValue('gender')">showValue</button>
        </div>
        <!-- สอน และให้ทำ select ประเทศ สักสามประเทศ -->
        <div class="inputContainer">
            <select v-model="province" >
                <!-- placeholder -->
                <option disabled>กรุณาเลือกจังหวัด</option>
                <option>เชียงใหม่</option>
                <option>กรุงเทศ</option>
            </select>
            <button @click="showValue('province')">showValue</button>
        </div>
        <!-- สอน date -->
        <div class="inputContainer">
            <p>วันเกิด</p>
            <input v-model="dob" type="date" />
            <button @click="showValue('dob')">showValue</button>
        </div>
    </div>
</template>

<script>
// 1. Define data first
// 2. make inputs
export default {
    data() {
        return {
            name: '',
            age: 0,
            address: '',
            isMarriaged: false,
            gender: 'male',
            province: '',
            dob: ''
        }
    },
    methods: {
        showValue: function (data) {
            console.log(data, this[data])
        }
    }
}
</script>

<style>
.inputContainer {
    margin-bottom: 16px;
}
</style>