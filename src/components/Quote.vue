<template>
  <div class="card-container col-6 col-sm-4 col-lg-3">
    <div class="card" @click="$emit('click')">
      <div class="card-body">
        {{ content }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['content']
}
</script>

<style scoped>
  .card-container {
    padding: 10px;
  }

  .card {
    height: 100%;
  }

  .card:hover {
    background: indianred;
    color: #fff;
    cursor: pointer;
  }
</style>
