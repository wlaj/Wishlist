<template>
<div>
    <div v-bind:key="wishlist.id" v-for="wishlist in wishlist">
    <h1>{{wishlist.title}}</h1>
    </div>
 </div>
</template>

<script>
export default {
    name: "Wishlist",
    props: ["wishlist"]
}
</script>

<style scoped>

</style>