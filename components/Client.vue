<template lang="pug">
  section
    .container.mod-client
      .m-auto.text-center
        h1 合作客戶
        p.pt-2.pb-4 良好的滿意度，來自我們專注的深度
      .row.no-gutters
        .col-6.col-md-3(:key="i", v-for="(image, i) in images")
          img(:src="require('~/assets/images/client/' + image.url + '.png')")
</template>

<script>
  export default {
    data () {
      return {
        images: [
          { url: 'FarEasTone' }, { url: 'hiiir' }, { url: 'imei' }, { url: 'heineken' }, { url: 'michelin' }, { url: 'anius' }, { url: 'tesa' }, { url: 'whoscall' }
        ]
      }
    }
  }
</script>

<style lang="scss" scoped>
  @import "~assets/scss/helpers";
  @import "~assets/scss/variables";

  .mod-client {
    h1 {
      font-size: 11vmin;
    }

    img {
      width: 100%;
      padding: 4vmin 10vmin;
    }

    @include media-breakpoint-up(sm) {
      h1 {
        font-size: 2.5rem;
      }

      img {
        padding: 4vmin 5vmin;
      }
    }

    @include media-breakpoint-up(xl) {
      img {
        padding: 20px 60px;
      }
    }
  }
</style>