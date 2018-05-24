<template lang="pug">
  section
    //- .background(
    //-   data-top-bottom="background-position: 50% -100px;",
    //-   data-bottom-top="background-position: 50% 100px;",
    //-   data-anchor-target="#features")
    .container
      h2.title 品質，是不妥協的堅持
      p.description 我們會確保每個製作的網站和軟體具備以下的品質
      .row
        .col-6.item
          fa.icon(:icon="['far', 'user']")
          h4.name 細緻高品質的介面視覺
        .col-6.item
          fa.icon(:icon="['far', 'user']")
          h4.name RWD 跨裝置瀏覽體驗
        .col-6.item
          fa.icon(:icon="['far', 'user']")
          h4.name 極具維護性的程式設計
        .col-6.item
          fa.icon(:icon="['far', 'user']")
          h4.name 可高度擴充的系統架構
        .col-6.item
          fa.icon(:icon="['far', 'user']")
          h4.name 清楚明瞭的自動化報表
        .col-6.item
          fa.icon(:icon="['far', 'user']")
          h4.name 高穩定性的伺服器建置
</template>

<script>
  export default {
    //
  }
</script>

<style lang="scss" scoped>
  @import "~assets/scss/helpers";
  @import "~assets/scss/variables";

  section {
    // @include parallax-background("https://picsum.photos/1920/1080?random=4") {
    //   @include background-mask;
    // }

    background-color: #fff;

    .container {
      padding: 25vmin 10vmin;
      text-align: center;
    }

    .title {
      font-size: 10vmin;
      font-weight: 600;
      padding-bottom: 5vmin;

      + .description {
        font-size: 4vmin;
        padding: 0 7vmin 4vmin;
        line-height: 1.75rem;
      }
    }

    .item {
      padding: 5vmin 4vmin;

      .icon {
        width: 3.215rem;
        height: 3.215rem;
        margin-bottom: 2vmin;
      }

      .name {
        font-size: 3.5vmin;
        font-weight: 500;
      }
    }
  }
</style>
