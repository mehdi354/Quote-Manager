<template>
  <div class="row">
    <div class="container">
      <quote v-for="(quote,index) in quotes" :key="index" :quote="quote" @click.native="deleteQuote(index)"></quote>
    </div>
  </div>
</template>
<script>
  import Quote from "./Quote.vue"
  export default{
    props : ["quotes"],
    components : {
        quote : Quote
    },
    methods:{
      deleteQuote(index){
        this.$emit("deleteQuote",index)
      }
    }
  }
</script>
<style></style>