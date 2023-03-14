<template>
  <div>
    <slot name="header" />
    <br />
    <el-input-number
      v-model="number"
      :min="min"
      :max="max"
      :step="step"
      :step-strictly="stepStrictly"
      :precision="precision"
      :controls="controls"
      :disabled="disabled"
      :placeholder="placeholder"
      :controls-position="controlsPosition"
      :size="sizes"
    />
    <br />
    <slot name="footer" />
  </div>
</template>

<script setup>
const props = defineProps({
  num: Number,
  min: {
    type: Number,
    default: -Infinity,
  },
  max: {
    type: Number,
    default: Infinity,
  },
  step: {
    type: Number,
    default: 1,
  },
  stepStrictly: {
    type: Boolean,
    default: false,
  },
  precision: Number,
  size: {
    type: String,
    default: 'default',
  },
  controls: {
    type: Boolean,
    default: false,
  },
  disabled: {
    type: Boolean,
    default: false,
  },
  controlsPosition: String,
  placeholder: String,
});
const number = ref('');
number.value = props.num;
</script>
