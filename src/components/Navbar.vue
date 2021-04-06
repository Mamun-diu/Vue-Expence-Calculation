<template>
    <nav>
        <button @click="openModel" class="btn">Add Expence</button>
    </nav>
</template>

<script>
export default {
    name: 'Navbar',
    methods:{
        openModel(){
            this.$emit('modelShow')
        }
    }
}
</script>

<style scoped>
    nav{
        width : 100%;
        height : 60px;
        background : #fff;
        box-shadow: 0 15px 30px rgba(0,0,0,0.1);
        display : flex;
        justify-content: center;
        align-items: center;
    }
    .btn{
        padding : 10px 14px;
        border : none;
        outline : none;
        background : rgb(16, 146, 146);
        color : #fff;
        border-radius: 3px;
        cursor: pointer;
        
    }
</style>