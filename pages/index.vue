<template lang="pug">
  .index
    u-banner(:with-title="true", :is-home="true", is-hero="true", hometitle="專注深刻", hometitle2="完美呈現", subtitle="我們專注於打造絕佳的網路產品", :is-video="true", img-url="https://picsum.photos/1920/540", :with-arrow="true", :class="{'home-hero': true}")
    section.main
      p.content
        | 悠夏爾科技以堅實的技術研發能力，結合美觀易用的介面設計、良好的使用者體驗，
        br.d-none.d-lg-block
        | 揉捻出最合適的商業解決方案，為您打造出色的網站與應用軟體。
    .row.no-gutters
      .col-md-6
        section.introduction.introduction-website
          h2.title
            span 絕佳設計
            span 美觀細膩
          p.content
            | 洞悉使用者操作習慣，透過美觀細膩的視覺設計，與易用性高的介面動線，
            | 讓您的網站在電腦與各個行動裝置上都擁有絕佳的使用體驗。
          nuxt-link.u-btn.u-btn-white(to="#") 了解服務項目
      .col-md-6
        section#parallax-alleylife.parallax.parallax-alleylife
          .background(
            data-top-bottom="background-position: 50% -100px;",
            data-bottom-top="background-position: 50% 100px;",
            data-anchor-target="#parallax-alleylife")
        section#parallax-cango.parallax.parallax-cango
          .background(
            data-top-bottom="background-position: 50% -100px;",
            data-bottom-top="background-position: 50% 100px;",
            data-anchor-target="#parallax-cango")
    .row.no-gutters
      .col-md-6
        section.introduction.introduction-function
          h2.title
            span 技術實力
            span 與時俱進
          p.content
            | 持續關注最新的網路技術，建構可高度擴充的系統架構，
            | 並保持充足的維護彈性和穩定性，滿足您所需要的各種技術支援和功能需求。
          nuxt-link.u-btn.u-btn-white(to="#") 了解服務項目
      .col-md-6.order-md-first
        section#parallax-tainan.parallax.parallax-tainan
          .background(
            data-top-bottom="background-position: 50% -100px;",
            data-bottom-top="background-position: 50% 100px;",
            data-anchor-target="#parallax-tainan")
        section.row.no-gutters.h-md-50
          section.col-6.h-md-100.image.image-employee
          section.col-6.h-md-100.image.image-office
    .row.no-gutters
      .col-md-6
        section.introduction.introduction-backend
          h2.title
            span 管理後台
            span 也能賞心悅目
          p.content
            | 悠夏爾所開發的網站內容管理系統「BACKEND」，
            | 提供美觀、直覺易用的後台介面，就連操作後台也能賞心悅目。
          nuxt-link.u-btn.u-btn-white(to="#") 了解服務項目
      .col-md-6
        section#parallax-backend.parallax.parallax-backend
          .background(
            data-top-bottom="background-position: 50% -100px;",
            data-bottom-top="background-position: 50% 100px;",
            data-anchor-target="#parallax-backend")
        section#parallax-big-backend.parallax.parallax-big-backend
          .background(
            data-top-bottom="background-position: 50% -100px;",
            data-bottom-top="background-position: 50% 100px;",
            data-anchor-target="#parallax-big-backend")
    u-features
</template>

<script>
  import UBanner from '~/components/Banner'
  import UFeatures from '~/components/Features'

  export default {
    components: { UBanner, UFeatures }
  }
</script>

<style lang="scss" scoped>
  @import "~assets/scss/helpers";
  @import "~assets/scss/variables";

  .index {
    .main {
      background-color: #fff;
      padding: 25vmin 10vmin;
      font-size: 4.5vmin;
      line-height: 8.5vmin;
      text-align: center;
    }

    .introduction {
      color: #fff;
      background-color: #262c32;
      padding: 25vmin 10vmin;

      .title {
        font-size: 11vmin;
        line-height: 14vmin;

        > * {
          display: block;
        }
      }

      .content {
        padding: 5vmin 0;
        line-height: 1.75rem;
      }
    }

    .parallax, .image {
      background-size: cover;
      background-position: center center;
      background-repeat: no-repeat;
    }

    .parallax {
      height: 50vh;

      &-alleylife {
        @include parallax-background("~assets/images/index/alleylife.jpg") {
          background-color: #efcc24;
        }
      }

      &-cango {
        @include parallax-background("~assets/images/index/cango.jpg") {
          background-color: #e0e0e0;
        }
      }

      &-tainan {
        @include parallax-background("~assets/images/index/tainan.jpg") {
          background-color: #fd5656;
        }
      }

      &-backend {
        @include parallax-background("~assets/images/index/backend.jpg") {
          background-color: #77c7c2;
        }
      }

      &-big-backend {
        @include parallax-background("~assets/images/index/big-backend.jpg");

        height: 50vh;
      }
    }

    .image {
      &-employee, &-office {
        height: 30vh;
      }

      &-employee {
        @include background("~assets/images/index/employee.jpg");
      }

      &-office {
        @include background("~assets/images/index/office.jpg");
      }
    }

    @include media-breakpoint-up(md) {
      .main {
        font-size: 1.32rem;
        line-height: 2.75rem;
        padding: 9.375rem 6.25rem;
      }

      .introduction {
        height: 130vh;
        padding: 0 20%;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        justify-content: center;

        .title {
          font-size: 3.3rem;
          line-height: 4rem;
        }

        .content {
          font-size: 1.1rem;
          line-height: 1.75rem;
          padding: 2.5rem 0;
        }
      }

      .parallax {
        height: 50%;
      }
    }
  }
</style>
