<template>
  <div class="container">
    <div class="row justify-content-md-center my-4">
      <div class="col-md-8 col-lg-6">
        <form @submit.prevent="onSubmit">
          <div class="form-group">
            <label for="myQuote">Quote</label>
            <textarea class="form-control" name="myQuote" rows="3" v-model="quote"></textarea>
          </div>

          <div class="text-center">
            <button type="submit" class="btn btn-primary">Save</button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data(){
      return {
        quote: ''
      }
    },
    methods: {
      onSubmit(){
        this.$emit('quoteAdded', this.quote);
        this.quote = '';
      }
    }
  }
</script>

<style scoped>
  label{
    font-weight: bold;
  }
</style>