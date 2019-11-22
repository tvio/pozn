<template>
    <div class="row">
        <app-pozn v-for="(pozn,index) in poznamky" @click.native="smazatPozn(index)" :key="index">
            {{pozn}}
        </app-pozn>
        </div>
</template>

<script>
import Pozn from './Pozn.vue';
export default {
      props: ['poznamky'],
      components:{
          appPozn: Pozn
      },
      methods: {
          smazatPozn(index){
            this.$emit('poznSmazana',index);
          }
      }
}
</script>

<style scoped>

</style>