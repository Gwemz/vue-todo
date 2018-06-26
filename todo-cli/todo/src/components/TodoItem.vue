<template>
    <li class="item" @click="handleDelete">{{content}}</li>
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
<style scoped>
.item{
    font-size:16px;
    /* color:#40a9ff ; */
    color:#666666;
    display: flex;
    align-items: center;
    justify-content: center;
}
</style>


