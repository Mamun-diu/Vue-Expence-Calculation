<template>
    <div v-if="status">
        <div class="model" @click.self="toggle">
            <div class="model__container">
                <div class="model__form">
                    <form @submit.prevent="addExpence" action="">
                        <div class="model__group">
                            <h3>Add Expence</h3>
                        </div>
                        <div class="model__group">
                            <input v-model="title" type="text" class="model__control" placeholder="Title...">
                        </div>
                        <div class="model__group">
                            <input v-model="number" type="number" class="model__control" placeholder="Expence...">
                        </div>
                        <div class="model__group">
                            <input class="button" type="submit" value="Add Expence">
                        </div>
                    </form>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name : "Model",
    props: ["status"],
    data(){
        return{
            title: '',
            number: null,
        }
    },
    methods:{
        toggle(){
            this.$emit("model-toggle")
        },
        addExpence(){
            this.$emit('store-expence',{title:this.title, number:this.number})
            this.title = '';
            this.number = null;
        }
    }
}
</script>

<style scoped>
    .model{
        position : fixed;
        top : 0;
        left : 0;
        width : 100%;
        height : 100%;
        background : rgba(0,0,0,0.5);
        display: flex;
        justify-content: center;
        align-items: center;
        z-index: 1;
    }
    .model__container{
        background : #fff;
        width : 450px;
        padding : 20px;
        border-radius: 5px;
    }
    .model__form{}
    .model__group{
        margin : 15px 0;
    }
    .model__control{
        border-bottom: 1px solid silver;
        border-left: none;
        border-right: none;
        border-top: none;
        width : 100%;
        padding : 7px 0;
        outline : none;
    }
    .button{
        padding : 10px 14px;
        border : none;
        outline : none;
        background : rgb(16, 146, 146);
        color : #fff;
        border-radius: 3px;
        cursor: pointer;
        width : 100%;
        
    }
</style>