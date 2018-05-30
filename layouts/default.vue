<template lang="pug">
  div
    transition(name="fade")
      u-loading(v-if="loading")
    u-header(:class="{ 'very-top': isVeryTop }")
    main
      nuxt
    u-footer
</template>

<script>
  import $ from 'jquery'
  import UHeader from '~/components/Header'
  import UFooter from '~/components/Footer'
  import ULoading from '~/components/Loading'

  export default {
    components: { UHeader, UFooter, ULoading },
    head () {
      return {
        meta: [
          { hid: 'og:url', name: 'og:url', content: location.href }
        ],
        link: [
          { hid: 'canonical', rel: 'canonical', href: location.href }
        ]
      }
    },
    data () {
      return {
        loading: true,
        isVeryTop: true
      }
    },
    mounted () {
      if (process.browser) {
        this.$nextTick(() => {
          $(window).scroll(() => {
            this.isVeryTop = $(window).scrollTop() > 10
          }).scroll()
        })
      }

      $(() => this.$nextTick(() => { this.loading = false }))
    }
  }
</script>

<style lang="scss">
  #__nuxt {
    min-height: 100vh;
    position: relative;
  }

  .fade-enter-active, .fade-leave-active {
    transition: opacity 1s;

    .u-loading-logo {
      transition: opacity .3s;
    }
  }

  .fade-enter, .fade-leave-to {
    &, .u-loading-logo {
      opacity: 0;
    }
  }
</style>

<style lang="scss" scoped>
  $footer-height: 6rem;

  main {
    padding-bottom: $footer-height;
  }

  footer {
    position: absolute;
    bottom: 0;
    width: 100%;
    height: $footer-height;
  }
</style>
