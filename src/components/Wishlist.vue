<template>
<div>
    <div v-bind:key="wishlist.id" v-for="wishlist in wishlist">
    <WishlistItem v-bind:wishlist="wishlist" v-on:del-wishlist="$emit('del-wishlist', wishlist.id)"/>
    </div>
 </div>
</template>

<script>
import WishlistItem from './WishlistItem.vue';

export default {
    name: "Wishlist",
    components: {
        WishlistItem
    },
   props: ["wishlist"]
}
</script>

<style scoped>

</style>