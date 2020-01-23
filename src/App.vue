<template>
  <div id="app">
    <Header />
    <AddWish />
    <Wishlist v-bind:wishlist="wishlist" v-on:del-wishlist="deleteWishlist" />
  </div>
</template>

<script>
import Header from './components/layout/Header';
import Wishlist from './components/Wishlist';
import AddWish from './components/AddWish';

export default {
  name: 'app',
  components: {
    Header,
    Wishlist,
    AddWish
  },
  data() {
    return {
      wishlist: [
        {
          id: 1,
          title: "Wishlist one",
          completed: false
        },
        {
          id: 2,
          title: "Wishlist two",
          completed: false
        },
        {
          id: 3,
          title: "Wishlist three",
          completed: false
        }
      ]
    }
  },
  methods: {
    deleteWishlist (id) {
      this.wishlist = this.wishlist.filter(wishlist => wishlist.id !== id);
    }
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
