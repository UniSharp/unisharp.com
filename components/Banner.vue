<template lang="pug">
  section.banner
    .banner-caption
      h3.text-uppercase(v-if="withTitle") We build great product
      h1(v-if="isHome")
        span {{ hometitle }}
        span {{ hometitle2 }}
      h1(v-else) {{ title }}
      p {{ subtitle }}
    .banner-background
      video(autoplay, loop, v-if="isVideo")
        source(src="~/assets/videos/banner.mp4", type="video/mp4")
      .banner-image(v-else, :style="`background-image: url(${imgUrl})`")
    .banner-mask
    .banner-logo
      nuxt-link(to="/")
        img(src="~/assets/images/logo.svg")
    .banner-arrow(@click="scroll", v-if="withArrow")
      .icon
</template>

<script>
  import $ from 'jquery'

  export default {
    data () {
      return {
        loading: true
      }
    },
    props: {
      withTitle: {
        type: Boolean,
        default: false
      },
      withArrow: {
        type: Boolean,
        default: false
      },
      isHome: {
        type: Boolean,
        default: false
      },
      isVideo: {
        type: Boolean,
        default: false
      },
      title: {
        type: String,
        required: true
      },
      subtitle: {
        type: String,
        required: true
      },
      hometitle: {
        type: String,
        required: true
      },
      hometitle2: {
        type: String,
        required: true
      },
      imgUrl: {
        type: String,
        required: true
      }
    },
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
    height: 70vh;

    &.home-hero {
      height: 100vh;
    }

    &-caption {
      text-align: center;

      h3, h1 {
        padding-bottom: 4vh;
      }

      h3 {
        font-size: 3vmin;
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

    &-image {
      @include background;

      height: 70vh;
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

    @include media-breakpoint-up(md) {
      &-caption {
        h3 {
          font-size: .9625rem;
          letter-spacing: .125rem;
          text-indent: .125rem;
          padding-bottom: 1.875rem;
        }

        h1 {
          font-size: 4.84rem;
          line-height: 5.5rem;
          padding-bottom: 1.5625rem;

          span {
            display: inline-block;
            padding: 0 .75rem;
          }
        }

        p {
          font-size: 1.1rem;
          letter-spacing: .3125rem;
          text-indent: .3125rem;
        }
      }

      &-logo {
        top: 3.25rem;
        left: 3.125rem;

        img {
          width: 10rem;
        }
      }

      &-arrow {
        bottom: 20%;
        margin-top: 4.375rem;
      }
    }
  }
</style>
