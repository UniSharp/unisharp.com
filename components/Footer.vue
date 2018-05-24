<template lang="pug">
  footer
    .container
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
  @import "~assets/scss/variables";

  footer {
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
