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
    .banner-logo
      nuxt-link(to="/")
        img(src="~/assets/images/logo.svg")
    .banner-arrow(@click="scroll")
      .icon
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

    &-logo {
      position: absolute;
      top: 2rem;
      left: 2rem;

      img {
        width: 8.125rem;
      }
    }

    &-arrow {
      @include transition(.3s);

      position: absolute;
      left: 50%;
      bottom: 13vh;
      width: 3.125rem;
      height: 3.125rem;
      margin-left: -1.5625rem;
      cursor: pointer;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;

      .icon {
        @include background("~assets/images/arrow-down-white.png");

        width: 1.875em;
        height: 1.875em;
      }

      &:hover {
        background-color: #fff;
        transform: rotate(360deg);

        .icon {
          background-image: url("~assets/images/arrow-down-black.png");
        }
      }
    }
  }
</style>
