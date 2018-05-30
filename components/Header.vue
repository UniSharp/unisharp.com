<template lang="pug">
  header
    button.u-menu-toggler(@click.prevent="opened = !opened")
      span.u-menu-toggler-icon
    .u-menu
      ul.list-unstyled.u-nav
        li.u-nav-item
          nuxt-link.u-nav-item-link(to="/") 首頁
        li.u-item
          nuxt-link.u-nav-item-link(to="/") 服務項目
        li.u-item
          nuxt-link.u-nav-item-link(to="/") 合作案例
        li.u-item
          nuxt-link.u-nav-item-link(to="/") 關於悠夏爾
        li.u-item
          nuxt-link.u-nav-item-link(to="/") 聯絡洽詢
      ul.list-unstyled.u-social
        li
          a(href="#", target="_blank")
            img(src="~/assets/images/icon/unisharp.svg")
        li
          a(href="#", target="_blank")
            img(src="~/assets/images/icon/github.svg")
        li
          a(href="#", target="_blank")
            img(src="~/assets/images/icon/fb.svg")
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
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background-color: rgba(255, 255, 255, .98);
    background-size: 101%;
    background-image: url("~assets/images/menu-bottom-bg.svg");
    background-repeat: no-repeat;
    background-position: center calc(100% + 1px);
    z-index: 90;
    padding: 0 1rem;
    transform: translateX(100%);

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
        }
      }
    }

    .u-social {
      display: flex;
      justify-content: center;
      margin-bottom: 2vh;

      li {
        width: 2.5rem;
        height: 2.5rem;
        margin: 0 1.3vh;
        border-radius: 50%;
        background-color: #262c32;

        a img {
          @include transition(.6s);
        }

        a:hover img {
          transform: rotate(360deg);
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
</style>
