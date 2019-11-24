<template>
  <div class="square_box">
      <div class="square">
          <span></span>
          <span></span>
          <span></span>
          <span></span>
          <div class="content">
              <h2>title</h2>
              <p>1231231231231231
                  23123123123123123
                  123123123123123123
                  123123123123</p>
              <a href="">123</a>
          </div>
      </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class HelloWorld extends Vue {
  @Prop() private msg!: string;
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        font-family: 'Open  Sans', sans-serif;
    }
    .square_box{
        margin: auto;
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100vh;
        height: 100vh;
        background: #000000;
        .square{
            display: flex;
            justify-content: center;
            align-items: center;
            background: #000000;
            position: relative;
            width: 400px;
            height: 400px;
        }
        .square span:nth-child(1),.square span:nth-child(2)
        ,.square span:nth-child(3),.square span:nth-child(4){
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: 2px solid #fff;
            border-radius: 38% 62%  63% 37% / 41% 44% 56% 59%;
            transition: .5s;
            animation: animate 4s linear infinite;
        }
        .square:hover span:nth-child(1),.square:hover span:nth-child(2),.square:hover span:nth-child(2)
        ,.square:hover span:nth-child(3),.square:hover span:nth-child(4){
            border: none;
            background: rgba(0,0,255,.8);
        }

        .square span:nth-child(2){
            animation: animate 6s linear infinite;
        }
        .square span:nth-child(3){
            animation: animate 8s linear infinite;
        }
        .square span:nth-child(4){
            animation: animate2 10s linear infinite;
        }

        @keyframes animate {
            0% {
               transform: rotate(0deg);
            }
            100% {
                transform: rotate(360deg);
            }
        }
        @keyframes animate2 {
            0% {
               transform: rotate(360deg);
            }
            100% {
                transform: rotate(0deg);
            }
        }
        .content{
            position: relative;
            padding: 40px 50px;
            color: #ffffff;
            text-align: center;
            transition: .5s;
            z-index: 1000;
            a{
                position: relative;
                display: inline-block;
                margin-top: 10px;
                border: 2px solid #ffffff;
                padding: 6px 18px;
                text-decoration: none;
                color:#ffffff;
                font-weight: 600;
                border-radius: 73%27%  44%56%  /49% 44% 56% 51%;
            }
            a:hover{
                background: #ffffff;
                color: #000000;
            }
        }
    }

</style>
