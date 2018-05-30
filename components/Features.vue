<template lang="pug">
  section
    .container
      h2.title 品質，是不妥協的堅持
      p.description 我們會確保每個製作的網站和軟體具備以下的品質
      .row
        .col-6.item
          img.icon(src="~/assets/images/quality/01.png")
          h4.name 細緻高品質的介面視覺
        .col-6.item
          img.icon(src="~/assets/images/quality/02.png")
          h4.name RWD 跨裝置瀏覽體驗
        .col-6.item
          img.icon(src="~/assets/images/quality/03.png")
          h4.name 極具維護性的程式設計
        .col-6.item
          img.icon(src="~/assets/images/quality/04.png")
          h4.name 可高度擴充的系統架構
        .col-6.item
          img.icon(src="~/assets/images/quality/05.png")
          h4.name 清楚明瞭的自動化報表
        .col-6.item
          img.icon(src="~/assets/images/quality/06.png")
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
