<template lang="pug">
  .index.container-fluid.px-0
    u-banner.mod-banner(title="合作案例", subtitle="力求完美呈現，不輕易放過每個微小細節", img-url="https://picsum.photos/1920/540")
    u-client.py-5
    section
      .mod-work.container
        .row.mx-0
          nuxt-link.card.col-md-6.my-md-4(:key="i", v-for="(card, i) in cards", :to="`/works/${card.name}`")
            .card-img-top(:style="`background-image: url(${require(`~/assets/images/works/list/${card.name}.jpg`)})`", alt="`${card.title}`")
            .card-body.bg-white
              h5.card-title {{ card.title }}
              p.card-text {{ card.content }}
</template>

<script>
  import UBanner from '~/components/Banner'
  import UClient from '~/components/Client'

  export default {
    components: { UBanner, UClient },
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
          },
          { name: 'avalue',
            title: '安勤科技',
            content: 'RWD 響應式設計-官方形象網站'
          },
          { name: 'kavalan',
            title: 'KAVALAN',
            content: 'RWD 響應式設計-官方形象網站'
          },
          { name: 'cango',
            title: '肯園芳香購物網',
            content: 'RWD 響應式設計-電子商務型網站'
          },
          { name: 'taiwan-news',
            title: '台灣英文新聞',
            content: 'RWD 響應式設計-新聞型網站'
          },
          { name: 'michelin',
            title: '米其林輪胎',
            content: 'RWD 響應式設計-電子商務型網站'
          },
          { name: 'whoscall',
            title: 'Whoscall 行銷活動',
            content: 'Mobile Web-韓國版整合行銷活動'
          },
          { name: 'tesa',
            title: 'TeSA 臺灣電子商務創業聯誼會',
            content: 'RWD 響應式設計-新聞型網站'
          },
          { name: 'taho',
            title: '泰合生技藥品',
            content: '企業官方網站'
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
      background-color: #f5f5f5;
    }

    .col-3 {
      align-items: center;
      display: flex;
      justify-content: center;
    }

    .mod-work {
      .card {
        border: 0;
        background-color: #f5f5f5;

        .card-img-top {
          @include background;

          height: 260px;

          @include media-breakpoint-between(sm,md) {
            height: 30.25vw;
          }
        }

        .card-body {
          text-align: center;
          padding-top: 25px;
          padding-bottom: 25px;

          .card-title {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 4px;
          }

          p {
            font-size: 1rem;
          }
        }
      }

      @include media-breakpoint-down(xs) {
        padding: 0 10vmin;

        .card {
          padding-right: 0;
          padding-left: 0;

          & + .card {
            margin-top: 25px;
          }

          .card-title {
            font-size: 6vmin;
          }

          .card-img-top {
            @include background;

            height: 42.857142857vw;
          }

          p {
            font-size: 4vmin;
          }
        }
      }
    }
  }
</style>
