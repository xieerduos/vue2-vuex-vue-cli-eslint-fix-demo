<template>
  <div id="app">
    <CountNumber></CountNumber>
  </div>
</template>

<script>
import CountNumber from '@/components/CountNumber.vue';
export default {
  name: 'App',
  components: {
    CountNumber
  },
  mounted() {
    console.log('this.$store', this.$store); 
  }
};
</script>

<style lang="scss"></style>
