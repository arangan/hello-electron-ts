<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
  props: {
    modelValue: String,
  },
  emits: ["update:modelValue"],
})
export default class InputExpandable extends Vue {}
</script>

<template>
  <span
    class="expandableParent"
    style="
      :focus-wthin {
        border-bottom: solid 1px;
      }
    "
  >
    <input
      class="inputExpandable"
      :value="modelValue"
      @input="$emit('update:modelValue', $event.target.value)"
    />
    <span class="spanExpandable">{{ modelValue }}</span>
  </span>
</template>
