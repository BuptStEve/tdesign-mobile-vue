<template>
  <div :class="name">
    <div v-if="title" :class="`${name}__title`">
      <slot name="title">
        {{ title }}
      </slot>
    </div>
    <div
      :class="{
        [`${name}__container`]: true,
        'border--top-bottom': bordered,
      }"
    >
      <slot></slot>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import config from '../config';
import CellGroupProps from './props';

const { prefix } = config;
const name = `${prefix}-cell-group`;

export default defineComponent({
  name,
  props: CellGroupProps,
  setup() {
    return { name };
  },
});
</script>
