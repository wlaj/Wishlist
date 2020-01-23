<template>
  <div id="app">
    <Wishlist v-bind:wishlist="wishlist" />
  </div>
</template>

<script>
import Wishlist from './components/Wishlist';

export default {
  name: 'app',
  components: {
    Wishlist
  },
  data() {
    return {
      wishlist: [
        {
          id: 1,
          title: "Todo one",
          completed: false
        },
        {
          id: 1,
          title: "Todo one",
          completed: false
        },
        {
          id: 1,
          title: "Todo one",
          completed: false
        }
      ]
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

</style>
