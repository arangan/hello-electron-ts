<template>
  <!-- <table class="header" id="tbody" border="1">
    <tr>
      <td colspan="7">
        <input-expandable v-model="docHeader.symbol" />
      </td>
    </tr>
    <tr>
      <td style="width: 8%">राग</td>
      <td style="width: 2%">:</td>
      <td style="width: 8%">
        <input-expandable v-model="docHeader.raagam" />
      </td>
      <td style="white-space: nowrap"></td>
      <td style="width: 8%">आराेह</td>
      <td style="width: 2%">:</td>
      <td style="width: 25%" class="leftAlign" nowrap>
        <input-expandable v-model="docHeader.arohanam" />
      </td>
    </tr>
    <tr>
      <td>ताल</td>
      <td>:</td>
      <td><input-expandable v-model="docHeader.taalam" /></td>
      <td>flex</td>
      <td>अवरोह</td>
      <td>:</td>
      <td nowrap class="leftAlign">
        <input-expandable v-model="docHeader.avarohanam" />
      </td>
    </tr>
  </table> -->
  <div class="grid">
    <div class="logo"><input-expandable v-model="docHeader.symbol" /></div>

    <div>राग</div>
    <div class="colon">:</div>
    <div class="leftAlign"><input-expandable v-model="docHeader.raagam" /></div>
    <div class="rightAlign">आराेह</div>
    <div class="colon">:</div>
    <div class="leftAlign">
      <input-expandable v-model="docHeader.arohanam" />
    </div>

    <div>ताल</div>
    <div class="colon">:</div>
    <div class="leftAlign"><input-expandable v-model="docHeader.taalam" /></div>
    <div class="rightAlign">अवरोह</div>
    <div class="colon">:</div>
    <div class="leftAlign">
      <input-expandable v-model="docHeader.avarohanam" />
    </div>
  </div>

  <br />
  <div class="docBody">
    <table id="tbl1" style="width: 100%; border: solid 1px black" border="1">
      <caption>
        Pallavi
      </caption>
      <tr>
        <td><input-expandable v-model="docBody[0]" /></td>
        <td><input-expandable v-model="docBody[1]" /></td>
        <td><input-expandable v-model="docBody[2]" /></td>
        <td><input-expandable v-model="docBody[3]" /></td>
        <td><input-expandable v-model="docBody[4]" /></td>
        <td><input-expandable v-model="docBody[5]" /></td>
        <td><input-expandable v-model="docBody[6]" /></td>
        <td><input-expandable v-model="docBody[7]" /></td>
        <td><input-expandable v-model="docBody[8]" /></td>
        <td><input-expandable v-model="docBody[9]" /></td>
      </tr>
    </table>
    <br />
    <div class="bodyGrid">
      <div><input-expandable v-model="docBody[0]" /></div>
      <div><input-expandable v-model="docBody[1]" /></div>
      <div><input-expandable v-model="docBody[2]" /></div>
      <div><input-expandable v-model="docBody[3]" /></div>
      <div><input-expandable v-model="docBody[4]" /></div>
      <div><input-expandable v-model="docBody[5]" /></div>
      <div><input-expandable v-model="docBody[6]" /></div>
      <div><input-expandable v-model="docBody[7]" /></div>
      <div><input-expandable v-model="docBody[8]" /></div>
      <div><input-expandable v-model="docBody[9]" /></div>

      <div><input-expandable v-model="docBody[0]" /></div>
      <div><input-expandable v-model="docBody[1]" /></div>
      <div><input-expandable v-model="docBody[2]" /></div>
      <div><input-expandable v-model="docBody[3]" /></div>
      <div><input-expandable v-model="docBody[4]" /></div>
      <div><input-expandable v-model="docBody[5]" /></div>
      <div><input-expandable v-model="docBody[6]" /></div>
      <div><input-expandable v-model="docBody[7]" /></div>
      <div><input-expandable v-model="docBody[8]" /></div>
      <div><input-expandable v-model="docBody[9]" /></div>
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import { DocHeader } from "./models/DocHeader";
import InputExpandable from "./components/InputExpandable.vue";
import "./assets/appStyles.css";
import "./assets/simpleGrid.css";

@Options({
  components: {
    InputExpandable,
  },
})
export default class App extends Vue {
  myData = "";
  docHeader = new DocHeader();
  docBody = new Array<Array<string>>(2);

  created(): void {
    console.log(this.myData);

    this.docHeader.raagam = "श्री";
    this.docHeader.taalam = "झप";
    this.docHeader.arohanam = "नि᳝ सा रे॒ म॔ प नि सां";
    this.docHeader.avarohanam = "सां नि ध॒ प म॔ ग रे॒ ग रे॒ रे॒ सा";
    this.docBody[0] = new Array<string>(10);

    this.docBody[0].push("Sa");
    this.docBody[0].push("re");
    this.docBody[0].push("ga");
    this.docBody[0].push("m");
    this.docBody[0].push("p");
    this.docBody[0].push("d");
    this.docBody[0].push("n");
    this.docBody[0].push("s");
    this.docBody[0].push("r");
    this.docBody[0].push("g");

    this.docBody[1] = new Array<string>(10);
    this.docBody[1].push("Sa");
    this.docBody[1].push("re");
    this.docBody[1].push("ga");
    this.docBody[1].push("m");
    this.docBody[1].push("p");
    this.docBody[1].push("d");
    this.docBody[1].push("n");
    this.docBody[1].push("s");
    this.docBody[1].push("r");
    this.docBody[1].push("g");
  }

  //eve.nextElementSibling;
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
