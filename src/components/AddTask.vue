<template>
  <form @submit="onSubmit" class="add-form">
    <div class="form-control">
      <label>Fullname</label>
      <input 
      type="text" 
      name="text"
      v-model="text" 
      placeholder="Jhon Doe" />
    </div>
    <div class="form-control">
      <label>Add Kr(sum)</label>
     <input 
        type="text"
        name="sum"
        v-model="sum"
        placeholder="Kr(sum)"
      />
      <label>Add (Kg)</label>
      <input 
        type="text"
        name="kg"
        v-model="kg"
        placeholder="Add Kg"
      />
    </div>
    <div class="form-control form-control-check">
      <label>Set Reminder</label>
      <input type="checkbox" v-model="reminder" name="reminder" />
    </div>
    <input 
    type="submit" 
    value="Click Me" 
    class="btn btn-block" />
  </form>
</template>

<script>
export default {
  data(){
    return{
      text:"",
      sum:"",
      kg :"",
      day:"",
      reminder:false
    }
  },
  methods:{
    onSubmit(e){
      e.preventDefault()
      if(!this.text && !this.sum && !this.kg) {
        alert('Please add a information')
        return
      }
      const newTask={
        id: Math.floor(Math.random() * 100000),
        text : this.text,
        sum : this.sum,
        kg : this.kg,
        reminder : this.reminder
      }
      this.$emit('add_task', newTask)
        this.text=""
        this.sum=""
        this.kg=""
        this.reminder=false

    }
  }

    
};
</script>

<style scoped>
.add-form {
  margin-bottom: 40px;
}
.form-control {
  margin: 20px 0;
}
.form-control label {
  display: block;
}
.form-control input {
  width: 100%;
  height: 40px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 17px;
  outline: none;
  border-radius: 6px;
  border-color: green;
}
.form-control textarea{
   width: 100%;
   font-size: 14px;
  height: 60px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 17px;
  outline: none;
  border-radius: 6px;
  border-color: green;

}
.form-control-check {
  display: flex;
  justify-content: space-between;
  align-items: center;
  
}
.form-control-check label {
  flex: 1;
}
.form-control-check input {
  flex: 2;
  height: 20px;
}
.btn-block {
  width: 100%;
}

</style>