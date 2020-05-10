<template>
  <div>
    <button v-on:click="onclick">押す</button>
    <span class="faces">{{ faces }}</span>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      faces: ""
    };
  },
  methods: {
    onclick() {
      this.faces = "🥺 ".repeat(Math.floor(Math.random() * 100));
    }
  }
};
</script>

<style scoped>
.faces {
  font-size: 32px;
}
</style>
