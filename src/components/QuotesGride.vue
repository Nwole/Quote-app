<template>
  <div class="grid-container">
    <Quote v-for="(quote, index) in myQuotes" :key="quote" @click.native="deleteQuote(index)"> {{ quote }}</Quote>
  </div>
</template>

<script>
import Quote from './Quote.vue';
export default {
    props: ["myQuotes"],
    data: () => {
       return {
       } 
    },
    methods:{
        deleteQuote(index){
            this.$emit('quoteDeleted', index)
        }
    },
    components: { Quote }
}
</script>

<style scoped>
    .grid-container {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 30px;
        width: 50%;
        margin: 20px;
    }
</style>