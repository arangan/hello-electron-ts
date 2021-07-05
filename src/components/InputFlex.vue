<style>
.flexContainer {
  position: relative;
  font-family: "myFirstFont";
  font-size: 25px;
}

.flexContainer:hover {
  border-bottom: solid 1px black;
}

.flexContainer::after {
  content: attr(data-value);
  color: red;
  white-space: pre-wrap;
  visibility: hidden;
}

.flexInput {
  position: absolute;
  width: 100%;
  font: inherit;
  min-width: 1ch;
  border: none;
  outline: none;
  margin: 0px;
  padding: 0px;
}
</style>
<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
  props: {
    modelValue: String,
  },
  emits: ["update:modelValue"],
})
export default class InputFlex extends Vue {
  defaultPlaceHolder = "·"; //"&middot;";
  // mdlValue = this.modelValue;

  mounted(): void {
    let el = document.getElementsByClassName("flexContainer");
    let inp = document.getElementsByClassName(
      "flexInput"
    )[0] as HTMLInputElement;

    console.log(el.length);
    let t = el[0] as HTMLSpanElement;
    console.log(t);

    t.dataset.value = inp.value;
  }

  Event_OnInput(
    inputElement: HTMLInputElement,
    parentElement: HTMLSpanElement
  ): void {
    parentElement.dataset.value =
      inputElement.value === "" ? this.defaultPlaceHolder : inputElement.value;
    this.$emit("update:modelValue", inputElement.value);
    console.log(parentElement.dataset.value);
  }
}
</script>

<template>
  <span class="flexContainer">
    <input
      class="flexInput"
      :value="modelValue"
      @input="Event_OnInput($event.target, $event.target.parentNode)"
      :placeholder="defaultPlaceHolder"
      size="1"
    />
  </span>
</template>
