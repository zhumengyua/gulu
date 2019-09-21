<template>
    <div class="row">
<slot>
    </div>
</template>

<script>
    export default {
        name:'GuluRow',
        props:{
span:Number
        }
    }
</script>

<style lang="scss" scoped>
.row{
    display:flex
}
</style>