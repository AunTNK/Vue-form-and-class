<template>
    <div>
        <h1>ได้รับวัคซีนรึยัง</h1>
        <input type="checkbox" v-model="isProtected" id="protected">
        <label for="protected">ได้รับวัคซีนแล้ว</label>
        <button @click="submit('isProtected')">Submit</button>
        <h1>chekbox แต่งงานรึยัง</h1>
        <div>
            <input type="checkbox" v-model="isMarriaged" id="marriaged">
            <label for="marriaged">แต่งงานแล้ว</label>
            <button @click="submit('isMarriaged')">Submit</button>
        </div>

        <h1>Radio</h1>
        <div>
            <div>เพศ</div>
            <input type="radio" v-model="gender" value="male" id="male">
            <label for="male">ชาย</label>
            <input type="radio" v-model="gender" value="female" id="female">
            <label for="female">หญิง</label>
            <button @click="submit('gender')">Submit</button>
        </div>
        <h1>Radio เลือก สัตว์ที่ชอบที่สุด จาก แมว หมา และ นก</h1>
        <div>
            <input type="radio" v-model="pet" value="cat" id="cat">
            <label for="cat">แมว</label>
            <input type="radio" v-model="pet" value="dog" id="dog">
            <label for="dog">สุนัข</label>
            <input type="radio" v-model="pet" value="brid" id="brid">
            <label for="brid">นก</label>
            <button @click="submit('pet')">Submit</button>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            isProtected: true,
            isMarriaged: false,
            gender: '',
            pet: 'dog'
        }
    },
    methods: {
        submit(inputName){
            // Input นี้มีค่า เท่าใด
            this.pet ? alert('Success’') : alert('Please enter ...')
            console.log(inputName,this[inputName])
        }
    }
}
</script>

<style>

</style>