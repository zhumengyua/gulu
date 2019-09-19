<template>
  <div class="warpprt" :class="{error}">
    <input type="text" :value="value" :disabled="disabled" :readonly="readonly" 
    @change="$emit('change', $event.target.value)"
      @input="$emit('input', $event.target.value)"
      @focus="$emit('focus', $event.target.value)"
      @blur="$emit('blur', $event.target.value)"
    />
    <!-- 第一个change事件是触发change事件（自己的) 后面的$event是为了触发原生的change事件 emit事件：第一个是事件名，第二个是传过去的第一个参数，后面可以跟很多个参数传过去。 -->
    <template v-if="error">
      <icon name="shibai" class="icon-error"></icon>
      <span class="errorMessge">{{error}}</span>
    </template>
  </div>
</template>

<script>
import Icon from "./icon";
export default {
  name: "gulu-Input",
  components: { Icon },
  props: {
    value: {
      type: String
    },
    disabled: {
      type: Boolean,
      default: false
    },
    readonly: {
      type: Boolean,
      default: false
    },
    error: {
      type: String
    }
  }
};
</script>

<style lang="scss" scoped>
$height: 32px;
$border-color: #999;
$border-color-hover: #666;
$border-radius: 4px;
$font-size: 12px;
$box-shadow-color: rgba(0, 0, 0, 0.5);
$red: #f1453d;
.warpprt {
  display: inline-flex;
  align-items: center;
  > :not(:last-child) {
    margin-right: 0.5em;

  }
  > input {
    height: 32px;
    border: 1px solid #999;
    border-radius: 4px;
    padding: 0 8px;
    font-size: 14px;
    &:hover {
      border-color: $border-color-hover;
    }
    &:focus {
      box-shadow: inset 0 1px 2px $box-shadow-color;
      outline: none;
    }
    &[disabled],
    &[readonly] {
      border-color: #ccc;
      color: #333;
      cursor: not-allowed;
    }
  }
  &.error {
    > input {
      border-color: $red;
    }
  }
  .icon-error {
    fill: $red;
  }
  .errorMessge {
    color: $red;
    font-size: 12px;
  }
}
</style>