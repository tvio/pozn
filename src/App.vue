<template>
    <div class="container">
        <app-lista :maximum="maximum" :pocet = "poznamky.length"></app-lista>
        <app-nova-pozn @poznPridana="pridej" >
    </app-nova-pozn>
    <app-pozn-tab :poznamky="poznamky"  @poznSmazana="smaz">
    </app-pozn-tab>
    <div class="alert alert-info">info: klikni na poznamku pro smazeni</div>
    </div>
</template>

<script>
import PoznTab from './components/PoznTab.vue';
import NovaPozn from './components/NovaPozn.vue';
import Lista from './components/Lista.vue';
    export default {
        data:function(){
            return{
                maximum: 10,
                poznamky:['První poznámka']
            }
        },
        components:{
            appPoznTab: PoznTab,
            appNovaPozn: NovaPozn,
            appLista: Lista
        },
        methods:{
            pridej(pozn){
                if (this.poznamky.length < 10) {
                this.poznamky.push(pozn);
                } else {
                 return alert('Prosím smažte poznámku');
                }


            },
            smaz(index){
                  this.poznamky.splice(index,1); 
                  console.log('smazano') ;
            } 
        }
    }
</script>

<style>
</style>
