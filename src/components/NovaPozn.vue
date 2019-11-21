<template>
    <div class="row">
      <form>
        <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
       <label>Pozn</label>
       <textarea class="form-control" rows="3" v-model="pozn"></textarea>
        </div>
         <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
             <button class="btn btn-primary" @click.prevent="createNew">Přidej pozn</button>
             </div>
        </form>
        </div>
</template>

<script>
import Pozn from './Pozn.vue';
export default {
data: function(){
     return {
         pozn:''
     };
},
methods: {
    createNew(){
        this.$emit('poznPridana',this.pozn);
        this.pozn = '';
    }
}
}
</script>

<style scoped>

</style>