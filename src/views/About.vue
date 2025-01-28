<script setup>
import { ref } from 'vue'
const show = ref(true)
const list = ref([1, 2, 3])
</script>
<template>
 <div class="body-text">
  <button @click="show = !show">Toggle List</button>
  <button @click="list.push(list.length + 1)">Push Number</button>
  <button @click="list.pop()">Pop Number</button>
  <button @click="list.reverse()">Reverse List</button>

  <ul v-if="show && list.length">
    <li v-for="item of list" :key="item">{{ item }}</li>
  </ul>

  <p v-else-if="list.length">List is not empty, but hidden.</p>
  <p v-else>List is empty.</p>
 </div>
</template>
<script>
    export default {
    name: 'About',
};
</script>
<style scoped>
   
h1 {
  color: red;
}
.body-text {
  position: absolute;
  top: 30%;
  left: 60%;
  transform: translate(-50%, -50%);
  width: 100%;
  text-align: left;
  padding: 0 30px;
}

.body-text div {
  font-size: 45px;
  font-weight: 600;
}
</style>