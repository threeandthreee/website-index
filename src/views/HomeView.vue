<template lang="pug">
v-container
  div.mx-auto.title-holder
    span.top-title 3
    span.top-title-middle and
    span.top-title 3
    span.top-title-middle .dev
  .d-flex.flex-column.align-center.mx-auto
    v-card.ma-1(outlined :width="width")
      v-card-title Projects
      v-card-text
        .d-flex.flex-column
          div
            a(href="https://vod-sync.3and3.dev")
              strong Vod Sync
            span &nbsp;- Sync youtube or twitch vods to a reference point and playback in sync.
      v-card-actions
        link-btn(url="https://github.com/alnordst" icon="github.svg" desc="Github")
        link-btn(url="https://codepen.io/alnordst" icon="codepen.svg" desc="Codepen")
    v-card.ma-1(outlined :width="width")
      v-card-title Art
      v-card-text
        .d-flex.flex-column
          div
            a(href="https://blog.3and3.dev")
              strong Blog
            span.ml-1 - Doodles, mostly.
          div
            a(href="https://3and3.the-comic.org")
              strong Comics
            span.ml-1 - An archive of comics I did years ago, but who knows, maybe I'll get back to it.
    v-card.ma-1(outlined :width="width")
      v-card-title Speedrunning
      v-card-text
        .d-flex.flex-column
          span I mostly just run a lot of <em>Metroid Dread</em>, though I'd like to get decent at <em>A Link to the Past</em> at some point. Oh, and not to brag, but I'm a world record holder in the ever popular speed game: <em>Desert Demolition featuring Road Runner and Wile E. Coyote</em>.
          v-divider.my-2
          personal-bests
      v-card-actions
        link-btn(url="https://twitch.tv/threeandthree" icon="twitch.svg" desc="Twitch")
        link-btn(url="https://www.speedrun.com/user/threeandthree" icon="src.png" desc="Speedrun.com")
        link-btn(url="https://racetime.gg/user/DMLq1oZAge3OeQG8" icon="racetime.svg" desc="Racetime.gg")
</template>

<script>
import LinkBtn from '../components/LinkBtn.vue'
import PersonalBests from '../components/PersonalBests.vue'

export default {
  data: () => ({
    width: 500
  }),
  components: {
    LinkBtn,
    PersonalBests
  }
}
</script>
