<script setup>
import { useRouter } from 'vue-router'

const router = useRouter()

const search = () => {
  const n = document.getElementById('n-value').value
  if (n && n > 0 && Number.isInteger(Number(n))) {
    router.push('/topnresults?n='+n)
  } else {
    alert('Please enter a positive integer')
  }
}
</script>

<template>
  <main>
    <h1>Enter Your N Value</h1>
    <input type="number" min="0" id="n-value" placeholder="Type your N" autocomplete="off" />
    <button type="button" @click="search">Search</button>
  </main>
</template>

<style scoped>
main {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 20px;
  height: 80%;
}

input {
  width: 400px;
  padding: 5px;
}

button {
  height: 60px;
  width: 200px;
  padding: 20px 40px;
  background-color: rgb(197, 196, 196);
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: rgb(177, 176, 176);
}
</style>