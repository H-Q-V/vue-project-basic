<script setup>
 import { reactive, ref } from 'vue';
 const todoData = reactive({
  email: '',
  name: '',
  phone: '',
  website: '',
 })
</script>

<template>
  <main style="color: #000; padding: 2rem;">
    <h1 style="font-weight: bold;">Create Todo</h1>
    <div style="margin-top: 2rem;">
      <input type="text" placeholder="Enter Email here" v-model="todoData.email">
    </div>
    <div style="margin-top: 2rem;">
      <input type="text" placeholder="Enter Name here" v-model="todoData.name">
    </div>
    <div style="margin-top: 2rem;">
      <input type="text" placeholder="Enter Phone here" v-model="todoData.phone">
    </div>
    <div style="margin-top: 2rem;">
      <input type="text" placeholder="Enter Website here" v-model="todoData.website">
    </div>
    <!-- <div class="btn-main">Create new</div> -->
    <div class="button-container">
      <button>Create new</button>
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
.button-container{
  display: flex;
  justify-content: flex-end;
  margin-top: 20px; 
}
button{
  padding: 0.8rem 0.8rem;
  border-radius: 6px;
}
button:hover{
  background-color: #CCFFFF;
}
</style>

