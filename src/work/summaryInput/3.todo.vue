<template>
    <div>
        <!-- <h1>โจทย์ สร้าง project ใหม่ Form add todo ที่ต้อง เพิ่ม สิ่งที่ต้องทำ
            แล้วให้ submit เป็น alert ออกมา </h1> -->
        <form @submit.prevent="submitTodo">
                <div>Add todo</div>
                <div>
                    <input type="text" v-model="todo" required>
                </div>
                <button type="submit">Submit</button>
        </form>
        <!-- slide signup work together -->
    </div>
</template>

<script>
export default {
    data() {
        return {
            todo: ''
        }
    },
    methods: {
        submitTodo() {
            alert('success add todo')
        }
    }
}
</script>

<style>

</style>