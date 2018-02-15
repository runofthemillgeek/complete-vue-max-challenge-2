<template>
  <div class="col-12 mt-2">
    <h2>Quote Organizer</h2>
    <div class="form-group">
      <label for="quoteInput">Enter a quote:</label>
      <input type="text" id="quoteInput" class="form-control" v-model="newQuote" @keydown.enter="addQuote">
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newQuote: ''
    }
  },

  methods: {
    addQuote: function() {
      this.$emit('newQuoteReceived', this.newQuote);
      this.newQuote = '';
    }
  }
}
</script>
