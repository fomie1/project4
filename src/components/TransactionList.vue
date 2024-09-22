<script setup>
    import {defineProps, defineEmits} from 'vue'

    const props = defineProps ({
        transactions: {
            type: Array,
            require: true,
        }
    })


    const emit = defineEmits(['transactionDeleted'])

    const deleteTransaction = (id) => {
        emit('transactionDeleted', id)
    }

</script>



<template>
    <h3>Games On Wishlist:</h3>
    <h5>Click the X to remove a wishlisted game</h5>
    <ul id="list" class="list">
        <li v-for="x in transactions" v-bind:key="x.id"
        v-bind:class="x.amount < 0 ? 'minus' : 'plus'">
        {{ x.text }} <span> ${{ x.amount }}</span>
        <button @click="deleteTransaction(x.id)" class="delete-btn">X</button>
    </li>
    
    </ul>


</template>