<template>
  <header>
      <h1>{{title}}</h1>
      <Button @toggle_add_task="$emit('toggle_add_task')"
       :text="showAddTask ? 'Close' : 'Add Info'"
       :color="showAddTask ? 'crimson' : 'green'" class="btn"/>
  </header>
</template>

<script>
import Button from '@/components/Button.vue'
export default {
    components:{
        Button,
    },
    props:{
        title:String,
        showAddTask:Boolean
    },

}
</script>

<style scoped>
header{
    display: flex;
    justify-content:space-between;
    align-content: center;
    margin-bottom: 20px;
     margin-top: 20px;
}

</style>