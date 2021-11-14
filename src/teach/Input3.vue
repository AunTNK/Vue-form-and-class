<template>
    <div>
        <h1>Select</h1>
        <div>จังหวัด</div>
        <select v-model="province">
            <option value="" disabled>กรุณาเลือกจังหวัด</option>
            <option >เชียงใหม่</option>
            <option >กรุงเทพ</option>
            <option >ขอนแก่น</option>
        </select>
        <button @click="submit('province')">Submit</button>
        <h1>โจทย์ select ประเทศ 3 ประเทศ</h1>
        <div>
            <div>ประเทศ</div>
            <select v-model="country">
                <option>ไทย</option>
                <option>อังกฤษ</option>
                <option>อเมริกา</option>
            </select>
            <button @click="submit('country')">Submit</button>
        </div>
        <h1>Date</h1>
        <div>
            <div>วันเกิด</div>
            <input type="date" v-model="dob">
            <button @click="submit('dob')">Submit</button>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            province: '',
            country: '',
            dob: ''
        }
    },
    methods: {
        submit(inputName){
            // Input นี้มีค่า เท่าใด
            console.log(inputName,this[inputName])
            if(inputName === 'dob') {
                console.log('date object', new Date(this.dob))
            }
        }
    }
}
</script>

<style>

</style>