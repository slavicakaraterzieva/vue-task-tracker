<template>
    <div v-on:click="$emit('toggle-reminder', task.id)"
        :class="[task.reminder ? 'reminder' : '', 'task']">

        <h3>{{task.text}}
            <i v-on:click="$emit('delete-task', task.id)" 
            class="fas fa-times"></i>
        </h3>
        <p>{{task.day}}</p>

    </div>
</template>

<script>
export default{
    name: 'Task',
    props: {
        task: Object,
    },
}
</script>

<style scope>
.fa{color:red}
.task{
    background: #f4f4f4;
    margin:5px;
    padding:10px 20px;
    cursor:pointer;
}
.reminder{
    border-left: 5px solid green;
}
.task h3{
    display:flex;
    align-items: center;
    justify-content: space-between;
}
</style>