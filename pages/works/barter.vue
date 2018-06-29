<template lang="pug">
  .index.container-fluid.px-0
    u-banner.mod-banner(title="小創客", subtitle="RWD 響應式設計-孩童換物教育平台", img-url="https://picsum.photos/1920/540")
    section
      .mod-work.container
        .text-box
          p 客製化藝術作品分享與換物平台，藉由作品創作創造價值，達成多面向教育意涵。目前即將成為台東縣政府推廣電腦教材的網站。
          a(href="https://www.barter.tw/", target="_blank") https://www.barter.tw/
        .main-pic
          a.btn.btn-dark(href="https://www.barter.tw/", role="button", target="_blank")
            span VISIT
            br
            span.ml-2.ml-md-0 PROJECT
            br
            fa.ml-2.ml-md-0(:icon="['fas', 'arrow-right']")
          img(src="~/assets/images/works/barter/barter.png")
        .sub-pic.mt-5
          p WEBSITE SCREENSHOT
          img(src="~/assets/images/works/barter/barter-3.png")
          img(src="~/assets/images/works/barter/barter-1.png")
          img(src="~/assets/images/works/barter/barter-2.png")
</template>

<script>
  import UBanner from '~/components/Banner'

  export default {
    components: { UBanner },
    data () {
      return {
        cards: [
          { name: 'barter',
            title: '小創客',
            content: 'RWD響應式設計-孩童換物教育平台'
          },
          { name: 'taya',
            title: '達亞帆布',
            content: 'RWD 響應式設計-官方形象網站'
          }
        ]
      }
    }
  }
</script>

<style lang="scss" scoped>
  @import "~assets/scss/helpers";
  @import "~assets/scss/variables";

  .index {
    section:not(.banner) {
      background-color: #fff;
    }

    .mod-work {
      @include media-breakpoint-down(sm) {
        padding: 0 10vmin;
      }

      img {
        width: 100%;
      }

      .text-box {
        margin: 0 auto;
        text-align: center;
        width: 100%;
        padding: 4rem 0;

        p {
          font-size: 4vmin;
          line-height: 28px;
        }

        a {
          font-size: 3vmin;
        }

        @include media-breakpoint-up(sm) {
          padding: 8rem 0 5rem;

          p {
            font-size: 1.2rem;
          }

          a {
            font-size: 1rem;
          }
        }

        @include media-breakpoint-up(lg) {
          width: 60%;
        }
      }

      .main-pic {
        position: relative;

        @include media-breakpoint-up(sm) {
          width: 100%;
          height: auto;
          margin: 5rem auto;
        }

        br {
          @include media-breakpoint-down(sm) {
            display: none;
          }
        }

        .btn {
          width: 70%;
          height: 50px;
          border-radius: 0;
          margin-bottom: 1rem;
          line-height: 2.5;
          transition: width .5s ease-out;

          @include media-breakpoint-up(sm) {
            text-align: left;
            padding: 1.5rem;
            letter-spacing: 2px;
            line-height: 1.5;
            position: absolute;
            left: 45px;
            top: -70px;
            width: 150px;
            height: 120px;
            font-size: 1rem;
            background-color: $gray-900;
            color: #fff;
            z-index: 2;
            border: 0;

            &:hover {
              border-color: $yellow;
              color: $gray-900;

              &:before {
                width: 100%;
              }
            }

            &:before {
              position: absolute;
              left: 0;
              top: 0;
              height: 100%;
              background-color: $yellow;
              transition: width .35s ease-out;
              width: 0;
              content: "";
              z-index: -1;
            }
          }
        }
      }

      .sub-pic {
        width: 80%;
        margin: 0 auto;

        @include media-breakpoint-down(sm) {
          width: 100%;
        }

        p {
          position: relative;
          padding-left: 2.5rem;
          font-weight: bold;
          margin-bottom: 1.5rem;

          &:before {
            content: "";
            width: 32px;
            width: 2rem;
            height: 1px;
            position: absolute;
            left: 0;
            top: 52%;
            margin-top: -.5px;
            display: inline-block;
            background-color: #3e3a39;
          }
        }

        img {
          margin-bottom: 3rem;
        }
      }
    }
  }
</style>
