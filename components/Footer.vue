<template lang="pug">
  footer
    section#contact.contact
      .background(
        data-top-bottom="background-position: 50% -100px;",
        data-bottom-top="background-position: 50% 100px;",
        data-anchor-target="#contact")
      .wrapper
        h6.title 與我們合作
        p.content 打造出色產品的任務，就交給專業的悠夏爾團隊吧
        nuxt-link.u-btn.u-btn-white(to="#") 聯絡洽詢
    .container-fluid
      p.copyright &copy; 2013 - 2018 UniSharp All rights reserved.
</template>

<script>
  import $ from 'jquery'

  export default {
    methods: {
      scroll () {
        $('html, body').stop(true, true).animate({ scrollTop: 0 })
      }
    }
  }
</script>

<style lang="scss" scoped>
  @import "~assets/scss/helpers";
  @import "~assets/scss/variables";

  .contact {
    @include parallax-background("~assets/images/index/contact.jpg") {
      @include background-mask(rgba(38, 44, 50, .85));
    }

    height: 28.125rem;
    color: #fff;
    display: flex;
    flex-direction: column;
    align-content: center;
    justify-content: center;

    .wrapper {
      padding: 0 2rem;
      text-align: center;

      .title {
        font-size: 2rem;
        margin-bottom: 1rem;
      }

      .content {
        margin-bottom: 2rem;
      }
    }
  }

  .container-fluid {
    background-color: #262c32;
    padding: 3.75rem 0;
    text-align: center;

    .copyright {
      color: rgba(255, 255, 255, .3);
      font-size: .75rem;
      letter-spacing: .0625rem;
    }
  }
</style>
