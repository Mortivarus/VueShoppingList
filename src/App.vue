<script setup>
let prodName = ["Brood", "Broccoli", "Krentenbollen", "Noten"]
let prodPrice = [1.00, 0.99, 1.20, 2.99]
let prodQuantity = []







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
            <td class="productPrice" id="number">1.00</td>
            <td><input type="number" class="productQuantity"></td>
            <td class="productTotalCost" id="number">0</td>
        </tr>
        <tr>
            <td>Broccoli</td>
            <td class="productPrice" id="number">0.99</td>
            <td><input type="number" class="productQuantity"></td>
            <td class="productTotalCost" id="number">0</td>
        </tr>
        <tr>
            <td>Krentenbollen</td>
            <td class="productPrice" id="number">1.20</td>
            <td><input type="number" class="productQuantity"></td>
            <td class="productTotalCost" id="number">0</td>
        </tr>
        <tr>
            <td>Noten</td>
            <td class="productPrice" id="number">2.99</td>
            <td><input type="number" class="productQuantity"></td>
            <td class="productTotalCost" id="number">0</td>
        </tr>
        <tr>
            <td colspan="3" id="total">Totaal</td>
            <td id="totalCost">0</td>
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
