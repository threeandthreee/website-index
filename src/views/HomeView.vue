<template lang="pug">
v-container
  div.mx-auto.title-holder
    span.top-title 3
    span.top-title-middle and
    span.top-title 3
    span.top-title-middle .dev
  .d-flex.flex-column.align-center.mx-auto(style="max-width:400px")
    v-card.ma-1(outlined)
      v-card-title Programming
      v-card-text
        .d-flex.flex-column
          div
            a(href="https://vod-sync.3and3.dev")
              strong Vod Sync
            span &nbsp;- Sync youtube or twitch vods to a reference point and playback in sync.
      v-card-actions
        link-btn(url="https://github.com/alnordst" icon="github.svg" desc="Github")
        link-btn(url="https://codepen.io/alnordst" icon="codepen.svg" desc="Codepen")
    v-card.ma-1(outlined)
      v-card-title Art
      v-card-text
        .d-flex.flex-column
          div
            a(href="https://blog.3and3.dev")
              strong Blog
            span.ml-1 - Doodles mostly, but some other stuff could end up here too.
          div
            a(href="https://3and3.the-comic.org")
              strong Comics
            span.ml-1 - An archive of comics I did years ago, but who knows, maybe I'll get back to it.
      v-card-actions
        link-btn(url="https://www.deviantart.com/aglari" icon="deviantart.svg" desc="DeviantArt")
    v-card.ma-1(outlined)
      v-card-title Speedrunning
      v-card-text
        span I hold the Road Runner world record in <strong>Desert Demolition featuring Road Runner and Wile E. Coyote</strong> and have monkeyed around with <strong>A Link to the Past</strong> a bit, but for the most part I just run a lot of <strong>Metroid Dread</strong>.
      v-card-actions
        link-btn(url="https://twitch.tv/threeandthree" icon="twitch.svg" desc="Twitch")
        link-btn(url="https://www.speedrun.com/user/threeandthree" icon="src.png" desc="Speedrun.com")
        link-btn(url="https://racetime.gg/user/DMLq1oZAge3OeQG8" icon="racetime.svg" desc="Racetime.gg")
</template>

<script>
import LinkBtn from '../components/LinkBtn.vue'
export default {
  components: {
    LinkBtn
  }
}
</script>
