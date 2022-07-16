<template lang="pug">
v-container
  div.mx-auto.title-holder
    span.top-title 3
    span.top-title-middle and
    span.top-title 3
    span.top-title-middle .dev
  .d-flex.flex-column.align-center.mx-auto
    v-card.my-2(outlined :width="width")
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
    v-card.my-2(outlined :width="width")
      v-card-title Art
      v-card-text
        .d-flex.flex-column
          v-row
            v-col(cols=6)
              v-card(href="https://blog.3and3.dev" hover height="150px" outlined)
                div(style="height:120px")
                  tumblr-preview(height="100%")
                .overline.text-center.mx-auto.py-auto Sketches
            v-col(cols=6)
              v-card(href="https://3and3.the-comic.org" hover height="150px" outlined)
                div(style="height:120px")
                  comic-preview(width="100%" height="100%")
                .overline.text-center.mx-auto.py-auto Comics
    v-card.my-2(outlined :width="width")
      v-card-title Speedrunning
      v-card-text
        .d-flex.flex-column
          span I mostly just run a lot of <em>Metroid Dread</em>, though I'd like to get decent at <em>A Link to the Past</em> at some point. Oh, and not to brag, but I'm a world record holder in the ever popular speed game: <em>Desert Demolition featuring Road Runner and Wile E. Coyote</em>.
          v-divider.my-2.d-none
          v-card.mt-3.mb-n3.py-2.pl-2(outlined)
            personal-bests
      v-card-actions
        link-btn(url="https://twitch.tv/threeandthree" icon="twitch.svg" desc="Twitch")
        link-btn(url="https://www.speedrun.com/user/threeandthree" icon="src.png" desc="Speedrun.com")
        link-btn(url="https://racetime.gg/user/DMLq1oZAge3OeQG8" icon="racetime.svg" desc="Racetime.gg")
</template>

<script>
import ComicPreview from '../components/ComicPreview.vue'
import LinkBtn from '../components/LinkBtn.vue'
import PersonalBests from '../components/PersonalBests.vue'
import TumblrPreview from '../components/TumblrPreview.vue'

export default {
  data: () => ({
    width: 500
  }),
  components: {
    ComicPreview,
    LinkBtn,
    PersonalBests,
    TumblrPreview
  }
}
</script>
