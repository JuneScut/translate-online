<template>
  <div id="translateOutput">
     <h1 class="text-primary">{{translatedText}}</h1>
  </div>
</template>

<script>
export default {
   name:'translateOutput',
   props:[
       'translatedText'
   ]
   
}
</script>

<style>
    .text-primary{
        color: #56CC9D;
    }
</style>
