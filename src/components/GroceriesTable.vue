<script setup>
import {computed} from 'vue'

const props = defineProps(['groceries'])

let total = computed(()=>{
    let total = 0

    for(let i in props.groceries){
        total += props.groceries[i].quantity * props.groceries[i].price
    }
    return total.toFixed(2)
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
    <tr v-for="i in props.groceries">
        <td>{{ i.name}}</td>
        <td>{{ i.price.toFixed(2) }}</td>
        <td><input type="number" class="productQuantity" v-model="i.quantity"></td>
        <td>{{ (i.price * i.quantity).toFixed(2) }}</td>
    </tr>
    <tr>
        <td colspan="3" id="total">Totaal</td>
        <td>{{ total }}</td>
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