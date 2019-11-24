<template>
  <div class="square_box">
      <div style="text-align: center">圆角旋转区域</div>
      <square style="width: 500px;height: 500px"></square>
      <div style="text-align: center">渐变背景色</div>
      <linear style="width: 500px;height: 500px"></linear>
      <div style="text-align: center">透明文字</div>
      <transparent-text></transparent-text>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import Square from "@/components/Square.vue";
import Linear from "@/components/linear.vue";
import TransparentText from "@/components/text/TransparentText.vue";
@Component({
    components: {TransparentText, Linear, Square}
})
export default class HelloWorld extends Vue {
  @Prop() private msg!: string;
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
