<script>
export default {
    data() {
        return {
            showDetailsstate: true
        }
    },
    props: {
        fullName: { type: String, required: true },
        phoneNumber: String,
        emailAddress: String,
        isFavorite: String
    },
    emits: ['toggle-favorite'],
    methods: {
        showDetails() {
            this.showDetailsstate = !this.showDetailsstate
        },
        toggleFavorite() {
            console.alert('togglecalled')
            this.$emit('toggle-favorite', this.id);
        }
    }

}
</script>

<template>
    <ul>
        <h2>{{ fullName }}</h2>
        <button @click="toggleFavorite()">Toggle Favorite</button>
        <button @click="showDetails()">Show Details</button>
        <ul v-if="showDetailsstate">
            <li>
                <strong>Phone: </strong>
                {{ phoneNumber }}
            </li>

            <li>
                <strong>Email: </strong>
                {{ emailAddress }}
            </li>
        </ul>
    </ul>
</template>
