<template>
  <div class="result">
    <div class="title">{{ results[resultIndex].title }}</div>
    <div class="desc">{{ results[resultIndex].desc }}</div>
  </div>
</template>
<script>
export default {
  props: ['results', 'totalCorrect'],
  computed: {
    resultIndex() {
      let value = 0;
      this.results.forEach((item, index) => {
        if (item.min <= this.totalCorrect && item.max >= this.totalCorrect) {
          value = index;
        }
      });
      return value;
    },
  },
};
</script>
