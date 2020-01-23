<template>
  <div id="app">
    <Header />
    <AddWish v-on:add-wish="addWish"/>
    <Wishlist v-bind:wishlist="wishlist" v-on:del-wishlist="deleteWishlist" />
  </div>
</template>

<script>
import Header from './components/layout/Header';
import Wishlist from './components/Wishlist';
import AddWish from './components/AddWish';
import axios from 'axios';

export default {
  name: 'app',
  components: {
    Header,
    Wishlist,
    AddWish
  },
  data() {
    return {
      wishlist: []
    }
  },
  // Hier is een fout
  methods: {
    deleteWish (id) {
      axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
      .then(res => this.wishlist = this.wishlist.filter(wishlist => wishlist.id !== id))
    },
    addWish(newWish) {
      const { title, completed } = newWish;

      axios.post('https://jsonplaceholder.typicode.com/todos', { title, completed })
      .then(res => this.wishlist = [...this.wishlist, newWish, res.data])
    }
  },
  created() {
    axios.get('https://jsonplaceholder.typicode.com/todos?_limit=10')
    .then(res => this.wishlist = res.data)
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Montserrat:300,400,500,700&display=swap');

  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
    font-family: 'Montserrat';
    line-height: 1.4;
  }

  .btn {
    display: inline-block;
    border: none;
    background: #555;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }

  .btn:hover {
    background: #666;
  }

</style>
