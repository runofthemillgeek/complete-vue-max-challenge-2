<template>
  <div class="col-12">
    <div class="progress">
      <div class="progress-bar" role="progressbar" :style="{ width: cssWidth }" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100">
        {{ displayValue }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['quotes', 'maxCount'],
  computed: {
    displayValue() {
      return this.quotes.length > 0 ? `${this.quotes.length} / ${this.maxCount}` : '';
    },

    cssWidth() {
      return this.quotes.length / this.maxCount * 100 + '%';
    }
  }
}
</script>
