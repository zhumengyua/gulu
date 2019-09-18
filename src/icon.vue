<template>

    <svg class="g-icon">
      <use :xlink:href="`#i-${name}`" />
    </svg>

</template>

<script>
import './svg'
export default {
    name:'gulu-buttonIcon',
    props:['name']
};
</script>

<style lang="scss" scoped>
        .g-icon {
          display: inline-block;
            width: 1em;
            height: 1em;
            vertical-align: -0.15em;
            fill: currentColor;
            overflow: hidden;
        }
</style>