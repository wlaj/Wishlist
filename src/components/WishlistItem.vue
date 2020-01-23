<template>
    <div class="wishlist-item" v-bind:class="{'is-complete':wishlist.completed}">
        <p>
        <input type="checkbox" v-on:change="markComplete">
        {{wishlist.title}}
        <button @click="$emit('del-wishlist', wishlist.id)" class="del">x</button>
        </p>
        </div>
</template>

<script>
export default {
    name: "WishlistItem",
    props: ["wishlist"],
    methods: {
        markComplete() {
            this.wishlist.completed = !this.wishlist.completed;
        }
    }
}
</script>

<style scoped>
.wishlist-item {
    background: #ccc;
    padding: 10px;
    border-bottom: 1px black dotted;
}

.is-complete {
    text-decoration: line-through;
}

.del {
    background: red;
    color: black;
}

</style>