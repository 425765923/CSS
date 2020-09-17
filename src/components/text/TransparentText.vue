<template>
  <div class="transparent_text">
      <h2>
          text
      </h2>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class TransparentText extends Vue {
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
    .transparent_text{
        font-size: 200px;
        font-weight: bold;
        letter-spacing: 20px;
        text-transform: uppercase;
        margin: auto;
        color: white;
        background: url("../../assets/logo.png") 50% 50%;
        background-size: cover;
        -webkit-text-fill-color: transparent;
        background-clip: content-box;
        text-align: center;
        -webkit-background-clip: text;
    }

</style>
