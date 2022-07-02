
<script>

import FriendContact from './components/FriendContact.vue'
import NewFriend from './components/NewFriend.vue'

export default {
  components: {
    FriendContact,
    NewFriend
  },
  data() {
    return{
      friends: [
      {
        id: 'manuel',
        name: 'Manuel Lorenz',
        phone: '011 1111222',
        email: 'manuel@localhost.com',
        isFavorite: true
      },
      {
        id: 'julie',
        name: 'Julie Salzburg',
        phone: '011 1111231',
        email: 'julie@localhost.com',
        isFavorite: true
      }
      ]
    }
  },
  methods: {
    toggleFavoriteStatus(friendId) {
      const identifiedFriend = this.friends.find(
        (friend) => friend.id === friendId
      );
      identifiedFriend.isFavorite = !identifiedFriend.isFavorite;
    },
    addContact(name, phone, email) {
      // const NewFriendContact = this. 

    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
<template>
<header>
  <h1>List of Friends, I guess!</h1>
</header>
<h2>Input Friends</h2>
<new-friend @add-contact="addContact"></new-friend>
<ul>
 <friend-contact 
 v-for ="friend in friends" :key="friend.id"
  :full-name="friend.name"
  :phone-number = "friend.phone"
  :email-address = "friend.email"
  :is-favorite = "friend.isFavorite"
  @favorite-toggle = "toggleFavoriteStatus"
 > </friend-contact>

</ul>
</template>

