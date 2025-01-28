<template>
  <div class="not-found">
    <h1>404 - Page Not Found</h1>
    <p>The page you're looking for doesn't exist.</p>
    <button @click="goHome">Go to Home</button>
  </div>
</template>

<script>
export default {
  name: 'NotFound',
  methods: {
    goHome() {
      this.$router.push('/');
    },
  },
};
</script>

<style scoped>
.not-found {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;
  height: 100vh;
  padding: 160px 20px 0;
}

h1 {
  color: red;
}

button {
  margin-top: 20px;
  padding: 10px 20px;
  font-size: 40px;
  cursor: pointer;
}
</style>
