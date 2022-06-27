<template>
    <form @submit.prevent="submitForm()">
        <div>
            <label>Name</label>
            <input type="text" v-model="enteredName">
        </div>

        <div>
            <label>Phone</label>
            <input type="tel" v-model="enteredName">
        </div>

        <div>
            <label>Email</label>
            <input type="email" v-model="enteredName">
        </div>
    </form>

    <div><button>Enter</button></div>
</template>

<script>
export default {
    data() {
        return {
            enteredName: '',
            enteredPhone: '',
            enteredEmail: ''
        }
    },
    emits: ['add-contact'],
    methods: {
        submitForm() {
            this.$emit('add-contact', this.enteredName, this.enteredPhone, this.enteredEmail)
        }
    }
}
</script>