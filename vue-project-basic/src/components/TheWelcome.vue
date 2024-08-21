<script setup>
const props = defineProps(['count']);
const emit = defineEmits(['handle-increase']);
const onIncrease = () =>{
   //console.log("Increase");
   emit('handle-increase',10);
}
</script>

<template>
   <div>Count: {{props.count}}</div>
   <button @click="onIncrease">Increase</button>
</template>