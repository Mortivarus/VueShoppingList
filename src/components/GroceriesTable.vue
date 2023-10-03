<script setup>
import {ref, computed} from 'vue'

const props = defineProps(['name', 'price'])

const quantity = ref([0, 0, 0, 0])

const totals =  computed(()=>{
    const list = []
    for (let i = 0; i < props.name.length; i++) {
        list[i] = (props.price[i] * quantity.value[i])
    }
    return list
})

const sumTotal = computed(()=>{
    const reducer = (accumulator, item) => {return accumulator + item}
    return totals.value.reduce(reducer, 0).toFixed(2)
})

</script>

<template>
<table>
    <tr>
        <th>Product</th>
        <th>Prijs</th>
        <th>Aantal</th>
        <th>Subtotaal</th>
    </tr>
    <tr v-for="i in name.length">
        <td>{{ props.name[i-1] }}</td>
        <td>{{ props.price[i-1].toFixed(2) }}</td>
        <td><input type="number" class="productQuantity" v-model="quantity[i-1]"></td>
        <td>{{ totals[i-1].toFixed(2) }}</td>
    </tr>
    <tr>
        <td colspan="3" id="total">Totaal</td>
        <td>{{ sumTotal }}</td>
    </tr>
</table>


</template>

<style scoped>
table{
    display: inline-table;
    border-collapse: collapse;
}

th, td, table{
    border: 1px solid #888;
    padding: 10px;
    font-family: sans-serif;
}

th{
    color: white;
    background-color: black;
    text-align: left;
}

#number, #totalCost, #total{
    text-align: right;
}
</style>