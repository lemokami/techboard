<script>
export default {
  props:{
    title:String,
    content:String,
    image:{
      type:String,
      required:false,
    },
  }
}
</script>
<template>
  <div class="border-2 border-gray-700 p-4 w-full h-full align-baseline">
    <div v-if="image">
    <img :src="image" alt="title">
    </div>
    <h3 class="font-medium text-2xl">{{title}}</h3>
    <p>{{content}}</p>
  </div>
</template>