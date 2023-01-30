<template>
    <h1>{{ header }}</h1>
    <input type="text" v-model="newItem" placeholder="Add an new item">
    <label for="">
        Priority:
        <select v-model="newItemPriority">
            <option value="low">Low</option>
            <option value="high">High</option>
        </select>
    </label>
    <br>
    {{ newItemPriority }}
    <ul>
        <li v-for="{id,label} in items" :key="id">{{ label }}</li>
    </ul>
    <p>What you like more?</p>
    <label>
        <input type="checkbox" value="chocolate" v-model="iceCreamFlavors">
    </label>
    <label>
        <input type="checkbox" value="Vanilla" v-model="iceCreamFlavors">
    </label>
    <label>
        <input type="checkbox" value="Strawberry" v-model="iceCreamFlavors">
    </label>
    <p>Ice cream flavors : {{ iceCreamFlavors }}</p>
    
</template>

<script>
export default {
    data() {
        return {
            header: 'Shopping List App',
            newItemPriority: 'low',
            newItem: '',
            items:[
                {id:1, label:"10 party hats"},
                {id:2, label:"16 party hats"},
                {id:3, label:"6 party hats"},
            ],
            iceCreamFlavors:[]

        }
        
    }
}
</script>

<style>
</style>