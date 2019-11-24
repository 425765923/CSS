<template>
  <div class="linear">

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
    .linear{
        width: 100vh;
        height: 100vh;
        background: linear-gradient(-45deg,#ee7752, #e73c7e, #23a6d5, #23d5ab);
        background-size: 400% 400%;
        animation: linearGradient 15s ease infinite;
        margin: auto;
    }
    @keyframes linearGradient {
        0%{
            background-position: 0% 50%;
        }
        50%{
            background-position: 100% 50%;
        }
        100%{
            background-position: 0% 50%;
        }
    }

</style>
