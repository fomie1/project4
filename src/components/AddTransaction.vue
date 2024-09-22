<script setup>
    import {ref, defineEmits} from 'vue'
    const text = ref('')
    const amount = ref('')

    const emit = defineEmits([
        'transactionSubmitted'
    ])

    const onSubmit = () =>{
        const transacitonData = {
            text: text.value,
            amount: parseFloat(amount.value),
        }

        emit('transactionSubmitted', transacitonData)

        text.value = ''
        amount.value = ''
    }

</script>


<template>
    <h3>Add a new Game</h3>
    <form id="form" @submit.prevent="onSubmit">
        <div class="form-control">
            <label for="text">Enter Game Name</label>
            <input type="text" id="text" v-model="text" placeholder="Cyberpunk 2077, Garry's Mod, Warhammer...">
        </div>
        <div class="form-control">
            <label for="amount">Enter Game Amount</label>
            <input type="text" id="amount" v-model="amount" placeholder="Is it worth it tho? Enter Amount...">
        </div>
        <button class="btn">Add To Your Wishlist</button>
    </form>
</template>