<template>
  <div  class="footer">
    <h4>Uzbekistan &copy;2022</h4>
    <a href="/">Telegram</a>
     <a href="/">Phone</a>
     <h4>Umid Shomurodov</h4>
    
  </div>
</template>

<script>
export default {
    props:{
        showAddTask:Boolean
    },
    data(){
      return{
     
      }
    }

}
</script>


<style scoped>
.footer{
    display: flex;
    align-items:center;
    justify-content: space-between;
    flex-wrap: wrap;
    margin-top: 40px;
    background: transparent;
    padding: 7px;
    color: green;
    border: 2px solid green;
    border-radius: 6px;
}
/* .footer:hover {
      background:green;
      color: white  ;
} */
.footer a{
  list-style: none;
  color:green;
 
}
.footer a:hover{
  text-decoration: none;

}

</style>