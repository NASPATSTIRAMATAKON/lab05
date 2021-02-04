<template>
<div>
    <h2>Books in Cart</h2>
    <div v-bind:key="book.bookid" v-for="book in cart">
        <CartItem v-bind:book="book" v-on:removeCartitem="Remove(book.bookid)" />
    </div>
</div>
</template>

<script>
import CartItem from './CartItem.vue';
export default {
    name: "Cart",
    props: ["cart"],
    components: {
        CartItem
    },
    methods:{
        Remove(bookId){
            this.$emit('removeCartitem',bookId);
        }
    }

}
</script>

<style scoped>
.book-item {
    background: #a1b5ca;
    padding: 10px;
    border-bottom: 1px rgb(230, 193, 193) dotted;
}
</style>
