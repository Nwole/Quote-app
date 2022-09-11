<template>
  <v-app>
    <NewQuote @quoteAdded="newQuote"/>
    <quotes-gride :myQuotes="quotes" @quoteDeleted="deleteQuote"></quotes-gride>
      <div class="w-full bg-cyan-200 border rounded-lg text-center text-base mt-20">
    <p>info: Click on a Quote to delete it</p>
  </div>
    <v-main>
      <router-view />
    </v-main> 
  </v-app>
</template>

<script>
import Header from "./components/Header.vue";
import QuotesGride from "./components/QuotesGride.vue";
import NewQuote from "./components/NewQuote.vue";

export default {
  name: "App",
  data() {
    return {
      quotes: ["just a quote to see something"],
      maxQuotes: 10,
    };
  },
  methods:{
    newQuote(quote){
      this.quotes.push(quote)
    },
    deleteQuote(index){
      this.maxQuotes.splice(index, 1)
    }
  },
  components: { Header, QuotesGride, NewQuote },
};
</script>
