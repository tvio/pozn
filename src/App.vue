<template>
    <div class="container">
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
    export default {
        data:function(){
            return{
                maxPozn: 10,
                poznamky:['První poznámka']
            }
        },
        components:{
            appPoznTab: PoznTab,
            appNovaPozn: NovaPozn
        },
        methods:{
            pridej(pozn){
                this.poznamky.push(pozn);

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
