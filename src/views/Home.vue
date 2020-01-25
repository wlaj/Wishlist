<template>
  <div id="app">
    <AddWish v-on:add-wish="addWish"/>
    <Wishlist v-bind:wishlist="wishlist" v-on:del-wishlist="deleteWishlist" />
  </div>
</template>

<script>
import Wishlist from '../components/Wishlist';
import AddWish from '../components/AddWish';


export default {
  name: 'app',
  components: {
    Wishlist,
    AddWish
  },
  data() {
    return {
      wishlist: [
        {
          id: 1,
          title: "Todo One",
          completed: false
        },
        {
          id: 2,
          title: "Todo One",
          completed: false
        },
        {
          id: 3,
          title: "Todo One",
          completed: false
        }
      ]
    }
  },
  methods: {
    deleteWish(id) {
      this.wishlist = this.wishlist.filter(todo => todo.id !== id);
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
