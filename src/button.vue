<template>
  <div>
    <button class="g-button" :class="{[`icon-${iconPosition}`]:true}" @click="$emit('click')">
      <g-icon class="icon" v-if="icon&&!loading" :name="icon"></g-icon>
      <g-icon class="loadding icon" v-if="loading" name="loading"></g-icon>
      <div class="content">
        <slot />
      </div>
    </button>
  </div>
</template>

<script>
export default {
  //props: ["icon", "iconPosition"]
  props: {
    icon: {},
    loading: {
      type: Boolean,
      default: false
    },
    iconPosition: {
      type: String,
      default: "left",
      //属性的检查器 验证iconPostition为left或right中的一个 return 非true
      validator(value) {
        return !(value !== "left" && value !== "right");
      }
    }
  }
};
</script>

<style lang="scss" scoped>
@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
.g-button {
  display: inline-flex;
  justify-content: center; //上下居中
  align-items: center; //水平居中
  //上面三句 居中
  vertical-align: middle; //和外部的元素对其
  //上下不对齐 就加这个
  font-size: var(--font-size);
  height: var(--button--height);
  padding: 0 0.6em;
  font: inherit;
  border-radius: var(--button-radius);
  border: 1px solid var(--border-color);
  background: var(--button-bg);
  //&表示当前选择器
  &:hover {
    border-color: var(--border-color-hover);
  }
  &:active {
    background-color: var(--button-active-bg);
  }
  &:focus {
    outline: none;
  }
  > .content {
    order: 2;
  }
  > .icon {
    order: 1;
    margin-right: 0.2em;
    margin-left: 0em;
  }

  &.icon-right {
    > .content {
      order: 1;
    }
    > .icon {
      order: 2;
      margin-right: 0;
      margin-left: 0.2em;
    }
  }
  .loadding {
    animation: spin 1.5s infinite linear;
  }
}
</style>