<template lang="pug">
  header
    button.u-menu-toggler(@click.prevent="opened = !opened")
      span.u-menu-toggler-icon
      span.u-menu-toggler-text 選單
    .u-menu
      .wrapper
        ul.list-unstyled.u-nav
          li.u-nav-item
            nuxt-link.u-nav-item-link(to="/")
              span.en index
              span.tw 首頁
          li.u-nav-item
            nuxt-link.u-nav-item-link(to="/")
              span.en service
              span.tw 服務項目
          li.u-nav-item
            nuxt-link.u-nav-item-link(to="/")
              span.en works
              span.tw 合作案例
          li.u-nav-item
            nuxt-link.u-nav-item-link(to="/")
              span.en about
              span.tw 關於悠夏爾
          li.u-nav-item
            nuxt-link.u-nav-item-link(to="/")
              span.en contact
              span.tw 聯絡洽詢
        ul.list-unstyled.u-social
          li
            a(href="#", target="_blank")
              img(src="~/assets/images/icon/unisharp.svg")
              span.text
                span.en blog
                span.tw 部落格
          li
            a(href="#", target="_blank")
              img(src="~/assets/images/icon/github.svg")
              span.text
                span.en open source
                span.tw 開放原始碼
          li
            a(href="#", target="_blank")
              img(src="~/assets/images/icon/fb.svg")
              span.text
                span.en facebook
                span.tw 臉書專頁
        ul.list-unstyled.u-contact
          li
            span TEL:
            | 02-25596680
          li
            span MAIL:
            | service@unisharp.com
          li
            span ADDRESS:
            | 10343 台北市大同區塔城街 66 號 7 樓之 1
</template>

<script>
  import $ from 'jquery'

  export default {
    data () {
      return {
        opened: false
      }
    },
    watch: {
      opened (value) {
        $('html')[['addClass', 'removeClass'][+value]]('u-menu-opened')
      }
    }
  }
</script>

<style lang="scss" scoped>
  @import "~assets/scss/helpers";
  @import "~assets/scss/variables";

  .u-menu-toggler {
    @include transition(.7s);
    @include border-radius(50%);

    position: fixed;
    top: .625rem;
    right: .625rem;
    width: 4rem;
    height: 4rem;
    padding: .625rem 1.25rem;
    background: transparent;
    border: none;
    outline: none !important;
    display: flex;
    align-items: center;
    cursor: pointer;
    z-index: 100;

    &-icon {
      position: relative;

      &, &:before, &:after {
        @include transition(.3s);

        flex: 0 0 auto;
        width: 1.5rem;
        height: .125rem;
        background-color: #fff;
      }

      &:before, &:after {
        content: "";
        position: absolute;
        left: 0;
      }

      &:before {
        top: -.55rem;
      }

      &:after {
        bottom: -.55rem;
      }
    }

    &-text {
      display: none;
    }

    &:hover &-icon {
      width: 1.05rem;

      &:after {
        width: .6rem;
      }
    }

    .very-top &, .u-menu-opened & {
      background-color: #262c32;
    }

    .very-top & {
      box-shadow: 0 0 6.25rem rgba(0, 0, 0, .3);
    }

    .u-menu-opened & {
      box-shadow: 0 0 1.875rem rgba(0, 0, 0, .3);

      &-icon {
        width: 0;
        background-color: rgba(255, 255, 255, 0);

        &:before, &:after {
          width: 1.5rem !important;
        }

        &:before {
          top: 0;
          transform: rotate(45deg);
        }

        &:after {
          bottom: 0;
          transform: rotate(-45deg);
        }
      }
    }
  }

  .u-menu {
    @include transition(.5s cubic-bezier(.17, .84, .38, 1));

    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    background-color: rgba(255, 255, 255, .98);
    background-size: 101%;
    background-image: url("~assets/images/menu-bottom-bg.svg");
    background-repeat: no-repeat;
    background-position: center calc(100% + 1px);
    z-index: 90;
    transform: translateX(100%);

    .wrapper {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 0 1rem;
      width: 100%;
      height: 100%;
    }

    .u-nav, .u-contact {
      width: 100%;
      text-align: center;
    }

    .u-nav {
      margin-bottom: 7vh;

      &-item {
        &-link {
          display: block;
          padding: 1.5vmin 0;
          font-size: 7vmin;
          font-weight: 600;

          .en {
            display: none;
          }
        }
      }
    }

    .u-social {
      display: flex;
      justify-content: center;
      margin-bottom: 2vh;

      li {
        margin: 0 1.3vh;

        a img {
          @include transition(.6s);

          width: 2.5rem;
          height: 2.5rem;
          border-radius: 50%;
          background-color: #262c32;
        }

        a:hover img {
          transform: rotate(360deg);
        }

        .text {
          display: none;
        }
      }
    }

    .u-contact {
      letter-spacing: 0;
      font-size: 3.5vmin;
      font-weight: 400;

      li {
        + li {
          margin-top: .5rem;
        }

        span {
          font-weight: 600;
          margin-right: .375rem;
        }
      }
    }

    .u-menu-opened & {
      transform: translateX(0);
    }
  }

  @include media-breakpoint-up(md) {
    .u-menu-toggler {
      top: 2.5rem;
      right: 2.5rem;
      width: 8rem;
      height: 3.125rem;
      padding: .1875rem 1.875rem;
      justify-content: space-between;
      border-radius: 12.5rem;

      &-text {
        display: block;
        color: #fff;
        font-size: .9625rem;
      }
    }

    .u-menu {
      .wrapper {
        display: flex;
        flex-flow: row wrap;
        align-items: center;
        align-content: center;
        justify-content: flex-start;
        max-width: 69rem;
        margin: auto;
        padding-bottom: 6.25rem;
      }

      > * {
        flex: 0 0 auto;
      }

      .en {
        font-size: .825rem;
        font-weight: 500;
        letter-spacing: .0625rem;
        opacity: .4;
        text-transform: uppercase;
      }

      .u-nav {
        margin-bottom: 6.125rem;
        display: flex;
        flex-wrap: wrap;

        &-item {
          flex: 0 0 auto;
          padding: 0 2.5rem;
          margin-bottom: 1.625rem;

          &-link {
            padding: 0;
            text-align: left;
            position: relative;

            .en, .tw {
              display: block;
            }

            .tw {
              font-size: 2.2rem;
              line-height: 1.1;
            }

            &:after {
              @include transition(.3s);

              content: "";
              position: absolute;
              left: 0;
              bottom: -.75rem;
              width: 0;
              height: .25rem;
              opacity: 0;
              background: #262c32;
            }

            &:hover:after {
              width: 100%;
              opacity: 1;
            }
          }
        }
      }

      .u-social {
        margin-bottom: 1rem;
        padding: 0 0 0 2.5rem;

        li {
          margin: 0 2.5rem 0 0;

          a {
            display: flex;
            align-items: center;

            .text {
              display: block;
              margin-left: 1rem;

              .en, .tw {
                display: block;
              }

              .tw {
                font-size: 1.1rem;
                font-weight: 600;
              }
            }
          }
        }
      }

      .u-contact {
        width: auto;
        padding: 0 2.5rem 0 0;
        font-size: .8943rem;
        letter-spacing: .0625rem;
        text-align: left;
        margin-left: auto;
      }
    }
  }
</style>
