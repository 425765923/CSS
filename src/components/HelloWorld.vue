<template>
  <div class="square_box">
      <div id="circle-btn">
          <div class="btn-container">
              <!--<embed src="../assets/next.svg" type="image/svg+xml" />-->
              <button><router-link :to="{name:'button'}">tz</router-link></button>
          </div>
      </div>
      <div style="text-align: center">圆角旋转区域</div>
      <square style="width: 500px;height: 500px"></square>
      <div style="text-align: center">渐变背景色</div>
      <linear style="width: 500px;height: 500px"></linear>
      <div style="text-align: center">透明文字</div>
      <transparent-text></transparent-text>
      <div style="text-align: center">Neumorphism</div>
      <n-box></n-box>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import Square from "@/components/Square.vue";
import Linear from "@/components/linear.vue";
import TransparentText from "@/components/text/TransparentText.vue";
import NBox from "@/components/box/nBox.vue";

@Component({
    components: {NBox, TransparentText, Linear, Square}
})
export default class HelloWorld extends Vue {
  @Prop() private msg!: string;
  mounted(){
      /**  add(1)(2)(3) = 6;
           add(1, 2, 3)(4) = 10;
           add(1)(2)(3)(4)(5) = 15;*/
      add()
  }
  public add(){
      a(1)(2)
      function a(..._args:any) {
          // 在内部声明一个函数，利用闭包的特性保存_args并收集所有的参数值
          var _adder = function() {
              _args.push(...arguments);
              return _adder;
          };

          // 利用toString隐式转换的特性，当最后执行时隐式转换，并计算最终的值返回
          _adder.toString = function () {
              debugger
              return _args.reduce(function (a:any, b:any) {
                  return a + b;
              });
          }
          return _adder;
      }
  }
  public jumpButton(){
      this.$router.push({name:'button'})
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    #circle-btn {
        display: flex;
        align-items: center;
        justify-content: center;
        height: 100vh;
    }

    .btn-container {
        position: relative;
    }

    button {
        border: 0;
        border-radius: 50px;
        color: white;
        background: #5f55af;
        padding: 15px 20px 16px 60px;
        text-transform: uppercase;
        background: linear-gradient(to right, #f72585 50%, #5f55af 50%);
        background-size: 200% 100%;
        background-position: right bottom;
        transition:all 2s ease;
    }

    svg {
        background: #f72585;
        padding: 8px;
        border-radius: 50%;
        position: absolute;
        left: 0;
        top: 0%;
    }

    button:hover {
        background-position: left bottom;
    }
</style>
