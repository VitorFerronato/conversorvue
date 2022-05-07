<template>
<div class="conversor">
    <h2>{{ moedaA }} to {{ moedaB }}</h2>
    <input type="number" v-model="moedaA_value" :placeholder="moedaA">
    <input class="button" type="button" value="Converter" @click="converter()">
    <h2>{{moedaB_value}}</h2>
</div>

</template>

<script>
export default{
    name: 'ConversorApp',
    props: ['moedaA', 'moedaB'],

    data() {
        return{
            moedaA_value: '',
            moedaB_value: 0
        }
    },

    methods: {
        converter() {
            //  SERVIDOR DA API FORA DO AR, CONSIDERANDO DOLLAR A R$ 5,08 ( Cotação  07/05/2022) -------

            // let de_para = this.moedaA_value + '' + this.moedaB_value
            // let url = `https://free.currconv.com/api/v7/convert?q=${de_para}&compact=ultra&apiKey=03944ee541bfa347c4a8`
            // fetch(url).then(res=>{return res.json})
            //             .then(json=> {
            //             let cotacao = json[de_para].val
            //             this.moedaA_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(2)
            // })

            let dollarValue = 5.08
            this.moedaB_value = (dollarValue * parseFloat(this.moedaA_value )).toFixed(2)
        }
    }
}

</script>

<style scoped>

    .conversor{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        max-width: 400px;
        min-width: 400px;
        padding: 20px;
        box-shadow: 0 4px 8px 0 rgba(0,0,0, .2);
        border-radius: 5px;
    }

    .button{
        margin-top: 1rem;
        padding: 10px;
        border-radius: 5px;
        background-color: #2c3e50;
        color: #fff;
        cursor: pointer;
        font-family: Arial, sans-serif;
        border: none;
        transition: .2s;
    }
    .button:hover{
        opacity: .8;
    }


</style>