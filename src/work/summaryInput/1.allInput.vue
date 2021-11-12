<template>
    <div>
        <div>
            <div>ชื่อ</div>
            <input type="text" v-model.trim="name" placeholder="กรุณากรอกชื่อจริง">
            <button @click="submit('name')">Submit</button>
        </div>
        <!-- <h1>โจทย์ input string เบอร์โทรศัพท์</h1> -->
        <!-- slide .trim -->
        <div>
            <div>เบอร์โทรศัพท์</div>
            <input type="text" v-model.trim="phone">
            <button @click="submit('phone')">Submit</button>
        </div>
        <!-- <h1>อีเมล มันจะตัด space ให้นะ แต่ บาง type อย่าง password ไม่ตัด</h1> -->
        <div>
            <div>password</div>
            <input type="password" v-model.trim="password">
            <button @click="submit('password')">Submit</button>
        </div>
        <!-- slide number -->
        <div>
            <div>อายุ</div>
            <input type="number" v-model.number="age">
            <button @click="submit('age')">Submit</button>
        </div>
        <!-- <h1>โจทย์ input number บอกจำนวนพี่น้อง</h1> -->
        <div>
            <div>มีพี่น้องกี่คน</div>
            <input type="text" v-model.number="bros">
            <button @click="submit('bros')">Submit</button>
        </div>
        <!-- slide .number -->
        <!-- slide other type -->
        <div>
            <div>ที่อยู่</div>
            <textarea v-model.trim="address" name="address" id="address" cols="30" rows="10"></textarea>
            <button @click="submit('address')">Submit</button>
        </div>
        <!-- <h1>โจทย์ textarea เกี่ยวกับตัวฉัน</h1> -->
        <div>
            <div>เกี่ยวกับตัวฉัน</div>
            <textarea v-model="aboutMe" name="aboutMe" id="aboutMe" cols="30" rows="10"></textarea>
            <button @click="submit('aboutMe')">Submit</button>
        </div>
        <!-- checkbox -->
        <div>
            <div>แต่งงานรึยัง</div>
            <input type="checkbox" v-model="isMarriaged" id="marriaged">
            <label for="marriaged">แต่งงานแล้ว</label>
            <button @click="submit('isMarriaged')">Submit</button>
        </div>
        <!-- <h1>โจทย์ checkbox ฉีดวัคซีนรึยังสิ</h1> -->
        <div>
            <div>ได้รับวัคซีน</div>
            <input type="checkbox" v-model="isProtected" id="protected">
            <label for="protected">ได้รับวัคซีนแล้ว</label>
            <button @click="submit('isProtected')">Submit</button>
        </div>
        <!-- จริงๆ สามารถใช้กับ อีกแบบเช่น รู้จัก website นี้จาก ที่ใด -->
        <!-- จะมาเฉลยทีหลังนะครับ -->
        <!-- radio -->
        <div>
            <div>เพศ</div>
            <input type="radio" v-model="gender" value="ชาย" id="male">
            <label for="male">ชาย</label>
            <input type="radio" v-model="gender" value="หญิง" id="female">
            <label for="female">หญิง</label>
            <button @click="submit('gender')">Submit</button>
        </div>
        <!-- <h1>โจทย์ radio สัตว์เลี้ยงที่ชอบ สัก 2 สามตัวเลือก</h1> -->
        <div>
            <div>สัตว์เลี้ยงที่ชอบที่สุด</div>
            <input type="radio" v-model="pet" id="dog" value="dog">
            <label for="dog">สุนัข</label>
            <input type="radio" v-model="pet" id="cat" value="cat">
            <label for="cat">แมว</label>
            <button @click="submit('pet')">Submit</button>
        </div>
        <!-- select -->
        <div>
            <div>จังหวัด</div>
            <select v-model="province">
                <option value="" disabled>กรุณาเลือกจังหวัด</option>
                <option value="Chiang mai">เชียงใหม่</option>
                <option>ลำพูน</option>
            </select>
            <button @click="submit('province')">Submit</button>
        </div>
        <!-- <h1>โจทย์ ประเทศที่อยากไปเที่ยว</h1> -->
        <div>
            <div>ประเทศที่อยากไปเที่ยวที่สุด</div>
            <select v-model="country">
                <option value="" disabled>กรุณาเลือกประเทศที่ต้องการ</option>
                <option value="USA">อเมริกา</option>
                <option value="China">จีน</option>
                <option value="England">อังกฤษ</option>
            </select>
            <button @click="submit('country')">Submit</button>
        </div>
        <!-- Date ลองทำตามได้เลยนะ -->
        <input type="date" v-model="dob">
        <button @click="submit('dob')">Submit</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            name: '',
            phone: '',
            age: 0,
            bros: 0,
            password: '',
            address: '',
            aboutMe: '',
            isMarriaged: false,
            isProtected: false,
            gender: '',
            pet: '',
            province: '',
            country: '',
            dob: ''
        }
    },
    methods: {
        submit(name) {
            // ชื่อ data และ ข้อมูลของ data
            console.log(name, this[name])
            if (name === 'dob') {
                const dateObj = new Date(this[name])
                console.log(name, dateObj)
            }
        }
    }
}
</script>

<style>

</style>