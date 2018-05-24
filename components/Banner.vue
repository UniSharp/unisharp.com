<template lang="pug">
  section.banner
    .banner-caption
      h3.text-uppercase We build great product
      h1
        span 專注深刻
        span 完美呈現
      p 我們專注於打造絕佳的網路產品
    .banner-background
    .banner-mask
    //- fa.arrow(:icon="['far', 'arrow-alt-circle-down']", size="3x", @click="scroll")
</template>

<script>
  import $ from 'jquery'

  export default {
    methods: {
      scroll () {
        $('html, body').stop(true, true).animate({ scrollTop: $(window).height() })
      }
    }
  }
</script>

<style lang="scss" scoped>
  @import "~assets/scss/helpers";
  @import "~assets/scss/variables";

  .banner {
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    color: #fff;
    width: 100%;
    height: 100vh;

    &-caption {
      text-align: center;

      h3, h1 {
        padding-bottom: 4vh;
      }

      h3 {
        font-size: 3vmin;
        font-size: .875rem;
        letter-spacing: .125rem;
        text-indent: .125rem;
        opacity: .4;
      }

      h1 {
        font-size: 16vmin;
        line-height: 20vmin;

        span {
          display: block;
        }
      }

      p {
        font-size: 4vmin;
        letter-spacing: .1875rem;
        text-indent: .1875rem;
      }
    }

    &-background, &-mask {
      position: fixed;
      top: 0;
      right: 0;
      bottom: 0;
      left: 0;
      z-index: -1;
    }

    &-background {
      background-image: url("https://picsum.photos/1920/1080?random=1");
      background-size: cover;
      background-repeat: no-repeat;
      background-position: center center;
    }

    &-mask {
      background-color: rgba(38, 44, 50, .8);
    }
  }

  // .banner {
  //   position: relative;
  //   display: flex;
  //
  //   &, .carousel, .img {
  //     width: 100%;
  //     height: 100vh;
  //   }
  //
  //   .banner-caption {
  //     position: absolute;
  //     top: 20%;
  //     right: 15%;
  //     bottom: 15%;
  //     left: 15%;
  //     display: flex;
  //     flex-direction: column;
  //     align-items: center;
  //     justify-content: center;
  //     background-color: transparent;
  //     color: $white;
  //     text-align: center;
  //
  //     h1 {
  //       font-size: 3rem;
  //       font-weight: 600;
  //
  //       @include media-breakpoint-up(md) {
  //         font-size: 4.5rem;
  //       }
  //     }
  //
  //     svg {
  //       width: 3rem;
  //       height: 3rem;
  //       cursor: pointer;
  //     }
  //   }
  //
  //   .carousel {
  //     position: fixed;
  //     top: 0;
  //     left: 0;
  //     z-index: -1;
  //
  //     .img {
  //       @include background;
  //       @include background-mask;
  //
  //       position: relative;
  //     }
  //   }
  // }
</style>
