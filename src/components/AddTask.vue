<template>
   <form @submit="onSubmit" class="add-form">

    <div class="form-control">
        <label>Task</label>
        <input type="text"
        placeholder="Add Task"
        v-model="text"/>
      </div>

      <div class="form-control">
        <label>Day</label>
        <input type="text" 
        placeholder="Add Day & Time"
        v-model="day"/>
      </div>

      <div class="form-control form-control-check">
        <label>Set Reminder</label>
        <input type="checkbox"
        v-model="reminder"/>
      </div>

      <input className="btn btn-block" type="submit" value="Save Task"/>

   </form>
</template>

<script>
export default{
    name: 'AddTask',
    data(){
        return{
            text: '',
            day: '',
            reminder: false
        }
    },
    methods:{
        onSubmit(e){
            e.preventDefault()
            if(!this.text){
                alert('Please Add a Task')
                return
            }
            const newTask={
                // id:Math.floor(Math.random()*1000),
                text:this.text,
                day:this.day,
                reminder:this.reminder
            }
            this.$emit('add-task',newTask)
            this.text=''
            this.day=''
            this.reminder=false
        }
    }
}
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
}
.form-control-check {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.form-control-check label {
  flex: 1;
}
.form-control-check input {
  flex: 2;
  height: 20px;
}
</style>