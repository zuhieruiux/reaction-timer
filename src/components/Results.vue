<template>
  <p>Reaction Time: {{ score }} ms</p>
  <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
  props: ["score"],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.score < 250) {
      this.rank = "You are Sanice";
    } else if (this.rank < 400) {
      this.rank = "Speed it's alright";
    } else {
      this.rank = "SLOWWWW!!!";
    }
  },
};
</script>

<style>
.rank {
  font-size: 1.4rem;
  color: #0faf87;
  font-weight: bold;
}
</style>
