<template>
  <div>
      <div>
          <button :class="tab === 1 ? 'activeMenu' : 'defaultMenu'" @click="to(1)">รายการอาหาร</button>
          <button :class="tab === 2 ? 'activeMenu' : 'defaultMenu'" @click="to(2)">สมาชิก</button>
          <button :class="tab === 3 ? 'activeMenu' : 'defaultMenu'" @click="to(3)">ตะกร้าสินค้า</button>
          <span v-show="cart">1</span>
      </div>
      <div>
          <div v-if="tab === 1">
              <h1>รายการอาหาร</h1>
              <div>
                  <img :src="krapraw.image" alt="">
                  <h2>{{ krapraw.title }}</h2>
                  <h4>{{ krapraw.description }}</h4>
                  <h4>{{ krapraw.price }} บาท</h4>
                  <button @click="addToCart(krapraw)">+</button>
              </div>
              <div>
                  <img :src="radna.image" alt="">
                  <h2>{{ radna.title }}</h2>
                  <h4>{{ radna.description }}</h4>
                  <h4>{{ radna.price }} บาท</h4>
                  <button @click="addToCart(radna)">+</button>
              </div>
          </div>
          <div v-if="tab === 2">
                <form @submit.prevent="submit">
                    <h1>สมาชิก</h1>
                    <div>
                        <input type="email" v-model="user.email">
                    </div>
                    <div>
                        <input type="password" v-model="user.password">
                    </div>
                    <div>
                        <button type="button">สมัครสมาชิก</button>
                        <button type="submit">เข้าสู่ระบบ</button>
                    </div>
                </form>
          </div>
          <div v-if="tab === 3">
              <h1>ตะกร้าสินค้า</h1>
              <div v-if="cart">
                  <img :src="cart.image" alt="">
                  <h2>{{ cart.title }}</h2>
                  <h4>{{ cart.description }}</h4>
                  <h4>{{ cart.price }} บาท</h4>
              </div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
    data: function() {
        return {
            tab: 2,
            krapraw: {
                image: "https://d12man5gwydfvl.cloudfront.net/wp-content/uploads/2019/03/%E0%B8%9C%E0%B8%B1%E0%B8%94%E0%B8%81%E0%B8%B0%E0%B9%80%E0%B8%9E%E0%B8%A3%E0%B8%B2%E0%B8%AB%E0%B8%A1%E0%B8%B9%E0%B8%AA%E0%B8%B1%E0%B8%9A-1.jpg",
                title: "ผัดกะเพรา",
                description: "ผัดกะเพราหมูสับ",
                price: 50,
            },
            radna: {
                image: "https://food.mthai.com/app/uploads/2017/07/noodle-with-pork-in-gravy.jpg",
                title: "ราดหน้า",
                description: "ราดหน้าหมูชิ้น เส้นหมีข่าว",
                price: 45,
            },
            cart: null,
            user: {
                email: '',
                password: ''
            },
        }
    },
    methods: {
        to: function(page) {
            if (this.tab === page) {
                this.tab = 0
            } else {
                this.tab = page
            }
        },
        addToCart: function(food) {
            this.cart = food
        },
        submit() {
            if(this.user.email && this.user.password) {
                alert('เข้าสู่ระบบสำเร็จ')
            } else {
                 alert('กรุณากรอกข้อมูลให้ครบถ้วน')
            }
        }
    }
}
</script>

<style>
img {
    height: 100px;
}
.activeMenu {
    background-color: crimson;
    color: white;
}
.defaultMenu {
    background-color: #EDEDED;
    border: none;
}
</style>