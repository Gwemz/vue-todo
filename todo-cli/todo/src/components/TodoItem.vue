<template>
    <li @click="handleDelete">{{content}}</li>
</template>
<script>
export default {
    props:['content','index'],
    methods:{
        handleDelete:function(){
            this.$emit('delete',this.index)
        }
    }
}
</script>
<style>

</style>


