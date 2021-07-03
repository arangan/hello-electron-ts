<template>
  <table class="header" id="tbody" border="1">
    <caption>
      ॐ
    </caption>
    <tr>
      <td>राग</td>
      <td>:</td>
      <td><input :value="modelValue.raagam" @input="Emit_Update" /></td>
      <td width="100%"></td>
      <td>आराेह</td>
      <td>:</td>
      <td nowrap>नि᳝ सा रे॒ म॔ प नि सां</td>
    </tr>
    <tr>
      <td>ताल</td>
      <td>:</td>
      <td>झप</td>
      <td></td>
      <td>अवरोह</td>
      <td>:</td>
      <td nowrap>सां नि ध॒ प म॔ ग रे॒ ग रे॒ रे॒ सा</td>
    </tr>
  </table>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import { DocHeader as IDocHeader } from "../models/DocHeader";

@Options({
  props: {
    modelValue: { type: Object as () => IDocHeader },
  },
  emits: ["update:modelValue"],
})
export default class DocHeader extends Vue {
  Emit_Update(evt: Event): void {
    let element = evt.target as HTMLElement;
    this.$emit("update:modelValue", element);
    // console.log($evt.target.value);
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@font-face {
  font-family: myFirstFont;
  src: url(../assets/siddhanta.ttf);
}
#tbody {
  font-family: "myFirstFont";
  font-size: 25px;
}
span.inp {
  background-color: yellow;
  margin: 0 0 0 0;
  border: 0px;
  outline: none;
  letter-spacing: 5px;
  background: rgb(16 119 24 / 0%);
}
table.header {
  width: 90%;
  max-width: 2480px;
  /* border: solid 1px black; */
  margin-left: 5%;
  margin-right: 5%;
}
table.header td {
  /* border:solid 1px black;  */
  padding-bottom: 7px;
}

.rightAlign {
  text-align: right;
}
.underLine {
  border-bottom: 2px solid black;
}
.colon {
  padding-left: 3px;
  padding-right: 5px;
  /* border:solid 1px black; */
}
</style>
