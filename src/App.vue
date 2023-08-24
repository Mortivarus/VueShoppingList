<script setup>
import {ref, reactive, computed} from 'vue'



let prodName = ["Brood", "Broccoli", "Krentenbollen", "Noten"]
let prodPrice = [1.00, 0.99, 1.20, 2.99]
let prodQuantity = ref([0, 0, 0, 0])

let prodTotals =  computed(()=>{
    let list = []
    for (let i = 0; i < prodName.length; i++) {
        list[i] = (prodPrice[i] * prodQuantity.value[i])
    }
    return list
})



let sumTotal = computed(()=>{
    const reducer = (accumulator, item) => {return accumulator + item}
    return prodTotals.value.reduce(reducer, 0).toFixed(2)
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
        <tr>
            <td>Brood</td>
            <td class="productPrice" id="number">{{ prodPrice[0].toFixed(2) }}</td>
            <td><input type="number" class="productQuantity" v-model="prodQuantity[0]"></td>
            <td class="productTotalCost" id="number">{{ prodTotals[0].toFixed(2)}}</td>
        </tr>
        <tr>
            <td>Broccoli</td>
            <td class="productPrice" id="number">{{ prodPrice[1].toFixed(2) }}</td>
            <td><input type="number" class="productQuantity" v-model="prodQuantity[1]"></td>
            <td class="productTotalCost" id="number">{{ prodTotals[1].toFixed(2)}}</td>
        </tr>
        <tr>
            <td>Krentenbollen</td>
            <td class="productPrice" id="number">{{ prodPrice[2].toFixed(2) }}</td>
            <td><input type="number" class="productQuantity" v-model="prodQuantity[2]"></td>
            <td class="productTotalCost" id="number">{{ prodTotals[2].toFixed(2)}}</td>
        </tr>
        <tr>
            <td>Noten</td>
            <td class="productPrice" id="number">{{ prodPrice[3].toFixed(2) }}</td>
            <td><input type="number" class="productQuantity" v-model="prodQuantity[3]"></td>
            <td class="productTotalCost" id="number">{{ prodTotals[3].toFixed(2)}}</td>
        </tr>
        <tr>
            <td colspan="3" id="total">Totaal</td>
            <td id="totalCost">{{ sumTotal }}</td>
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
