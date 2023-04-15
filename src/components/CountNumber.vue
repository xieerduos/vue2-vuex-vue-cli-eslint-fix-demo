<template>
  <div class="counter-number">
    <!-- 显示count 的值 -->
    <h1>{{ count }}</h1>
    <button @click="incrementCount">increment</button>
  </div>
</template>
<script>
import {mapState, mapMutations} from 'vuex';
export default {
  name: 'CountNumber',
  data() {
    return {};
  },
  computed: {
    ...mapState(['count'])
  },
  methods: {
    ...mapMutations(['increment']),
    incrementCount() {
      this.increment();
    }
  }
};
</script>
