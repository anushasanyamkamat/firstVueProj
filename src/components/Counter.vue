<template>
    <div>
        <button @click="decrease"> - </button>
            {{ count }}
        <button @click="increase"> + </button>
        <p class="green" :class="{'red':isRed}"> 
            {{ msg }}
        </p>
    </div>
</template>

<script>
export default {
    name: 'Counter',
    props : {
        defaultCount: Number,
        minCount: Number,
        maxCount: Number
    },
    data: function(){
        return{
            count: this.defaultCount,
            msg: '',
            isRed : false
        }
    },
    methods:{
        decrease: function(){
            if(this.count > this.minCount){
                this.count--;
                this.msg = "The Counter has been decreased to " + this.count;
                this.isRed = false;
            }
            else{
                this.msg = "The Counter cannot be decreased below " + this.minCount;
                this.isRed = true;
            }
        },
        increase: function(){
            if(this.count < this.maxCount){
                this.count++;
                this.msg = "The Counter has been increased to " + this.count;
                this.isRed = false;
            }
            else{
                this.msg = "The Counter cannot be increased after " + this.maxCount;
                this.isRed = true;
            }
        }
    }
    
}
</script>

<style>
.green{
    color: green;
}

.red{
    color: red;
}

</style>