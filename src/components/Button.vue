<template>
    <button type="button" @click="onClick" :style="{background:color}" class="btn">{{text}}</button>
</template>
<script>
export default {
    name: 'Button',
props: {
    text: String,
    color: String
},
methods: {
    onClick(){
        //console.log("clicked")
        this.$emit('toggle-add-task')
    }
 }
}
</script>