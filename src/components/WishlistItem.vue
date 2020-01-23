<template>
    <div>
        <p>Wishlist item</p>
        </div>
</template>

<script>
export default {
    name: "WishlistItem"
}
</script>

<style scoped>
.wishlist-item {
    background: white;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
}

.is-complete {
    text-decoration: line-through;
}

</style>