<template>
    <div class="converterDiv">
        <h2>{{currencyA}} to {{currencyB}}</h2>
        <input :placeholder="currencyA" v-model="currencyA_value" type="text">
        <input type="button" value="Converter" v-on:click="converterApi">
        <h2>{{currencyB_value}}</h2>
    </div>
  
</template>

<script>

export default {
    name:"Converter",
    props: ["currencyA", "currencyB"],
    data(){
        return{
            currencyA_value:"",
            currencyB_value: 0,
        };
    },
    methods:{
        converterApi(){
            let fromTo = this.currencyA + "_" + this.currencyB;
            console.log(fromTo)
            let url = "https://free.currconv.com/api/v7/convert?q=" + fromTo + "&compact=ultra&apiKey=d30c50d9bda1b54a758f";

            fetch(url)
            .then(res=> {
                
                return res.json();
                })
                .then(json =>{
                    console.log(json);
                    let exchangePrice = json[fromTo];
                    this.currencyB_value = (exchangePrice * parseFloat(this.currencyA_value)).toFixed(2);
                    
            });
        }
    }
}
</script>

<style scoped>
.converterDiv{
    padding: 20px;
    max-width: 300px;
    box-shadow: 0 4px 4px 0 rgba(0, 0, 0,0.2);
}
</style>