<script setup>
import GroceriesTable from './components/GroceriesTable.vue'


const name = ["Brood", "Broccoli", "Krentenbollen", "Noten"]
const price = [1.00, 0.99, 1.20, 2.99]
</script>

<template>


    <GroceriesTable :price="price" :name="name"/>


</template>


