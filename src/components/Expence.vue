<template>
    
    <div class="">
        <div class="expences">
            <div class="balance">
                <span>Balance</span>
                <p>{{allExpences.balance}}</p>
            </div>
            <div class="income">
                <span>Income</span>
                <p>{{allExpences.income}}</p>
            </div>
            <div class="expence">
                <span>Expence</span>
                <p>{{allExpences.expence}}</p>
            </div>
        </div>

        <div v-for="history in allExpences.history" :key="history.title">
            <div :class="(history.number > 0)?'green':'red'" class="history">
                <div class="history__title">{{ history.title }} </div>
                <div class="history__number">{{ history.number }} </div>
            </div>
            
        </div>
    </div>
   
</template>

<script>
export default {
    name: 'Expence',
    props:['allExpences']
}
</script>

<style scoped>
    .expences{
        width : 700px;
        margin : 70px auto;
        display : flex;
        justify-content:space-between
    }
    .balance, .income, .expence{
        background : #fff;
        padding : 20px;
        box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        width : 200px;
        height : 150px;
        display : flex;
        justify-content: center;
        align-items: center;
        position : relative;
        

    }
    .balance{
        border-bottom: 4px solid orange;
    }
    .income{
        border-bottom: 4px solid blue;
    }
    .expence{
        border-bottom: 4px solid brown;
    }
     span{
        position : absolute;
        top : 0;
        left : 0;
        
        color : #fff;
        font-size: 12px;
        padding : 5px ;
    }
    .balance span{
        background : orange;
    }
    .income span{
        background : blue;
    }
    .expence span{
        background : brown;
    }
    p{
        font-size : 20px;
    }

    .history{
        width : 400px;
        margin : 0 auto;
        display: flex;
        justify-content: space-between;
        background: #fafafa;
        color : rgb(51, 90, 63);
        padding : 10px 15px;
        margin-bottom : 5px;
        box-shadow: 0 0 15px rgba(0,0,0,0.1);
        animation: animate 0.5s linear;
    }
    @keyframes animate{
        from{
            opacity : 0;
        }to{
            opacity : 1;
        }
    }
    .history__title{
        width: 300px;
    }
    .history__number{
        width : 80px;
    }
    .red{
        border-left : 3px solid red;
    }
    .green{
        border-left : 3px solid rgb(34, 240, 154);
    }
</style>