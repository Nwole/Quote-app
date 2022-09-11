<template>
  <div>
    <form class="form">
      <label>Quote</label>
      <v-textarea
        v-model="quote"
        label="write your quote here"
        auto-grow
        outlined
        rows="5"
      ></v-textarea>
      <div class="btn-control">
        <v-btn class="btn-btn ma-2 bg-indigo-600" @click.prevent="createNew" outlined> Add Quote </v-btn>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      quote: "",
    };
  },
  methods:{
    createNew(){
      if(this.quote.trim() !== '')
      
        this.$emit('quoteAdded', this.quote)
        this.quote = ''
    }
  }
};
</script>

<style>
.header {
  width: 80%;
  height: 100%;
  margin: auto;
}
.form {
  width: 50%;
  margin: auto;
}

.btn-btn {
  color: white;
}
</style>
