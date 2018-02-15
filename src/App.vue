<template>
  <div class="container">
    <main class="row mt-5">
      <app-quotes-meter :quotes="quotes" :maxCount="MAX_COUNT"></app-quotes-meter>
      <app-quote-input @newQuoteReceived="addQuote"></app-quote-input>
      <app-quotes-list :quotes="quotes" @onQuoteTapped="removeQuote"></app-quotes-list>
      <app-info-box></app-info-box>
      <app-footer></app-footer>
    </main>
  </div>
</template>

<script>
import QuotesMeter from './components/QuotesMeter';
import QuoteInput from './components/QuoteInput';
import InfoBox from './components/InfoBox';
import QuotesList from './components/QuotesList';
import Footer from './components/Footer';

export default {
  data() {
    return {
      MAX_COUNT: 10,
      quotes: [
        'Hello, world!',
        'Whaddup',
        `
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Et porro dolor voluptatum optio quisquam enim recusandae, tempore magni assumenda autem, sint dolores pariatur omnis consequuntur vel accusamus, laborum fugit odio.
        `,
        'Whaddup',
        'Hello, world!'
        ]
    }
  },

  components: {
    'app-quotes-meter': QuotesMeter,
    'app-quote-input': QuoteInput,
    'app-quotes-list': QuotesList,
    'app-info-box': InfoBox,
    'app-footer': Footer
  },

  methods: {
    removeQuote: function(i) {
      console.log(this.quotes.splice(i, 1));
    },

    addQuote: function(q) {
      if (this.quotes.length >= this.MAX_COUNT) {
        alert(`Can't add more than ${this.MAX_COUNT} quotes. Please remove some.`);
        return;
      }

      this.quotes.push(q);
    }
  }
}
</script>

<style>
  @import '~bootstrap/dist/css/bootstrap.min.css';

  main {
    padding-bottom: 50px;
    position: relative;
  }
</style>
