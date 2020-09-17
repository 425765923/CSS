<template>
    <!-- https://juejin.im/post/6868099832175820808 -->
    <div class="nBox">
        <div class="card right">
            <div class="card left"></div>
        </div>

        <div class="card right2">
            <div class="card left2"></div>
        </div>
    </div>
</template>

<script lang="ts">
    import {Component, Prop, Vue} from 'vue-property-decorator';

    export default class nBox extends Vue {

    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">


    /* 设置一些页面的布局样式 */
    .nBox {
        /* 定义变量 */
        --bgColor: #ff5353;

        /* rgba的四个值分别为：红(R)、绿(G)、蓝(B)、透明度(A) */
        --whiteShadow: -15px -15px 25px rgba(255, 117, 117, .5);
        --blackShadow: 15px 15px 25px rgba(110, 40, 40, .2);

        --whiteShadow2: 15px 15px 25px rgba(255, 117, 117, .5);
        --blackShadow2: -15px -15px 25px rgba(110, 40, 40, .2);

        display: flex;
        margin: auto;
        padding: 0;
        width: 50vw;
        height: 50vh;
        justify-content: center;
        align-items: center;
        background-color: var(--bgColor);

        .card {
            width: 30vh;
            height: 30vh;
            /* margin: 45px; */
            background-color: var(--bgColor);
            border-radius: 30px;
        }

        /* 主要部分 */
        .left {
            box-shadow: inset var(--blackShadow),
            inset var(--whiteShadow);
        }

        .right {
            box-shadow: var(--blackShadow),
            var(--whiteShadow);
            padding: 5px;
        }

        .left2 {
            box-shadow: inset var(--blackShadow2),
            inset var(--whiteShadow2);
        }

        .right2 {
            box-shadow: var(--blackShadow),
            var(--whiteShadow);
            padding: 5px;
            margin: 50px;
        }
    }

</style>
