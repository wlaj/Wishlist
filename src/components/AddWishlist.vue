<template>
    <div>
        <form>
        <input type="text" name="title" placeholder="Add wishlist..">
        <input type="submit" value="Submit" clas="btn">
        </form>
        </div>
</template>

<script>
export default {
    name: 'AddWishlist'
}
</script>

<style scoped>
form {
    display: flex;
}

input[type="text"] {
    flex: 10;
    padding: 50px;
}

input[type="submit"] {
    flex: 2;
}

</style>