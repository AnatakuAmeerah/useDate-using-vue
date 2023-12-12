

<template>
  <div>
     <h2>The Date is: {{ dateFormatted }}</h2>
     <div class="btn">
     <button @click="addDay(1)">Adds one day</button>
     <button @click="addMonth(1)">Adds one month</button>
    </div>
  </div>
 </template>
 
 <script>
 import { ref, computed } from 'vue';
 export default {
  setup() {
     const date = ref(new Date());
 
     const addDay = (days) => {
       date.value = new Date(date.value.getTime() + days * 24 * 60 * 60 * 1000);
     };
 
     const addMonth = (months) => {
       date.value = new Date(date.value.getFullYear(), date.value.getMonth() + months, date.value.getDate());
     };
 
     const dateFormatted = computed(() => date.value.toLocaleDateString());
 
     return { dateFormatted, addDay, addMonth };
  },
 };
 </script> 




