<template>
<div>
    <ul class="navbar">
        <li><button class=" btn btn-sm btn-secondary">Flexbox</button></li>
        <li><button class=" btn btn-sm btn-secondary">Border</button></li>
    </ul>
</div>
</template>

<script>
export default {
    data: function(){
        return{
            name: "This is navbar"
        }
    }
}
</script>

<style scoped>
div{
    background-color: aquamarine;
}
.navbar{
    list-style: none;
    display: flex;
    justify-content: center;
    align-items: center;
}
.btn{
margin: auto 10px;
}
</style>