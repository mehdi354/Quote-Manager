<template>
    <div>
        <headercom :quoteCount="quotes.length" :maxQuote="maxQuote"></headercom>
        <newQuote @addNew="addNewQuote"></newQuote>
        <quoteGrid :quotes="quotes" @deleteQuote="deleteQuotes"></quoteGrid>
    </div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid.vue'
import NewQuote from './components/NewQuote.vue'
import Headercom from './components/Headercom.vue'
export default {
  name: 'app',
  components: {
    quoteGrid   : QuoteGrid,
    newQuote    : NewQuote,
    headercom      : Headercom
  },
  data(){
    return {
        quotes : [
            "So many books, so little time."
        ],
        maxQuote : 10
    }
  },
  methods : {
    addNewQuote(quote){
        console.log(quote);
        if(this.quotes.length >= this.maxQuote) {
            alert("Please delete some");
        }
        else{
            this.quotes.push(quote)
        }
    },
    deleteQuotes(index){
        this.quotes.splice(index,1)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  overflow-x: hidden;
}
</style>
