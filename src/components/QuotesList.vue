<template>
  <div class="col-12">
    <div class="row align-items-stretch">
      <app-quote v-for="(content, i) in quotes" :key="i" :content="content" @click="onClick(i)"></app-quote>
    </div>
  </div>
</template>

<script>
import Quote from './Quote.vue';

export default {
  props: ['quotes'],
  components: {
    'app-quote': Quote
  },
  methods: {
    onClick: function(i) {
      console.log('clickeed?');
      this.$emit('onQuoteTapped', i);
    }
  }
}
</script>

