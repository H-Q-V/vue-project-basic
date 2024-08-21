<script setup>
import { onMounted, ref } from 'vue';
import { useRouter } from 'vue-router';
const router = useRouter();
const user = ref([]);
onMounted(()=>{
  (async() => {
    const res = await fetch('https://jsonplaceholder.typicode.com/users')
    const data = await res.json();
    user.value = data;
  })(); 

  // fetch('https://jsonplaceholder.typicode.com/users')
  //     .then(response => response.json())
  //     .then(json => user.value = json);
})
</script>

<template>
  <main style="color: #000; padding: 2rem;">
    <input type="text" placeholder="Enter search here">
    <div class="group-card">
      <div class="card-item" v-for="todo in user">
       <div @click="router.push({path:`/todo/${todo?.id}`})">
        <h2>{{ todo?.name }}</h2>
        <i>{{ todo?.email }}</i>
       </div> 
      </div>
    </div>
  </main>
</template>
<style>
input {
   width: 100%;
   padding: .6rem 1.2rem;
   border-radius: 50px;
   border: none;
   outline: none;
   background: #ededed;
}
.group-card{
  margin-top: 1.5rem;
  display: flex;
  flex-direction: column;
  row-gap: 1.5rem;
}
.card-item{
  border-radius: 10px;
  background: #324558;
  color: #fff;
  cursor: pointer;
  padding: .8rem 1rem;
}
.card-item:hover {
  background: #243241;

}
</style>

