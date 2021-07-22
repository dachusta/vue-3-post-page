<template>
  <div class="page__wrapper">
    <div
      v-for="number in total"
      :key="number"
      class="page"
      :class="{
        'current-page': page === number
      }"
      @click="$emit('change', number)"
    >
      {{ number }}
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      total: {
        type: Number,
        required: true
      },
      page: {
        type: Number,
        required: true
      }
    }
  }
</script>

<style scoped>
.page__wrapper {
  display: flex;
  margin-top: 15px;
}
.page {
  height: 45px;
  width: 45px;
  text-align: center;
  border: 1px solid teal;
  padding: 10px;
  cursor: pointer;
}
.current-page {
  border: 2px solid teal;
  color: white;
  background: teal;
}
</style>