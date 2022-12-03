<template>
  <div class="block" v-if="showBlock" @click="stopTimer">Quick! Click me!</div>
</template>

<script>
export default {
  props: ["delayTime"],
  data() {
    return {
      showBlock: false,
      timer: null,
      reactionTimer: 0,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer();
    }, this.delayTime);
  },
  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.reactionTimer += 10;
      }, 10);
    },
    stopTimer() {
      clearInterval(this.timer);
      this.showBlock = false;
      this.$emit("endTimer", this.reactionTimer);
    },
  },
};
</script>

<style>
.block {
  width: 400px;
  border-radius: 20px;
  background: #0faf87;
  color: white;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}
</style>
