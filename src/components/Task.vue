<template>
  <div @dblclick="$emit('toggle_reminder',task.id)" :class="[task.reminder ? 'reminder' :'','task']" class="task">   
        <h3>{{task.text}}
           <i @click="$emit('delete_task',task.id)" class="fas fa-times">x</i>
        </h3>
        <!-- <p>{{task.sum}}</p> -->
        <h4>{{ 
        (((parseInt(task.sum) + parseFloat(task.sum/100)) * 130) + (parseInt(15000) * parseFloat((task.kg)))) +  " " + 'sum'
            }}</h4>
  </div>
  
</template>

<script>
export default {
    props:{
        task:Object,
    }
}
</script>

<style scoped>
.fas{
    color: crimson;
    font-weight: bold;
    cursor: pointer;
}
.task{
    background: rgb(230, 226, 226);
    margin: 5px;
    padding: 10px 20px;
    width: 100%;
    display: block;
    cursor: pointer;
    transition: .5s;

   
}
.task:hover{
    background: whitesmoke

}
.task.reminder{
    border-left: 5px solid green;
}
.task h3{
    display: flex;
    justify-content:space-between;
    align-items: center;
}
.task p{
    margin-top: 10px;
    font-size: 12px;
    height: 15px;
}


</style>