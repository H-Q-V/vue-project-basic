<script setup>
import { onMounted, ref } from 'vue';
import { useRoute } from 'vue-router';
const router = useRoute();
const user = ref(null);
onMounted(()=>{
  (async() => {
    const res = await fetch(`https://jsonplaceholder.typicode.com/users/${router.params.id}`);
    const data = await res.json();
    user.value = data;
  })(); 
});
</script>

<template>
  <main style="color: #000; padding: 2rem;">
    <!-- Todo Item {{ router.params.id }} -->
     <div class="card-item">
       <h2>{{ user?.email }}</h2>
       <h3>{{ user?.name }}</h3>
       <div>{{ user?.username }}</div>
       <div>{{ user?.phone }}</div>
       <div>{{ user?.website }}</div>


       <div>Delete</div>
     </div>
  </main>
</template>
