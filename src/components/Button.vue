<template>

  <button @click="$emit('toggle_add_task')"
   :style="{background:color}">
   {{text}}
   </button>
</template>

<script>
export default {
    props:{
        text:String,
        color:String 
    },
   
}
</script>

<style>

</style>