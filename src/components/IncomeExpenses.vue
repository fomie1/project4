<script setup>
    import {defineProps} from 'vue'

    const props = defineProps({
        income: {
            type: Number,
            require: true,
        },
        expense: {
            type: Number,
            require: true,
        }
    })

</script>




<template>
    <div class="inc-exp-container">


        <h4>Total Price of Wishlist</h4>
        <p id="money-minus" class="money minus">-${{ income }}</p>

       <!-- <div>
            
        </div> -->
        <!--<div>
            <h4>Expense</h4>
            <p id="money-minus" class="money minus">-${{ expense }}</p>
        </div> -->
    </div>

</template>