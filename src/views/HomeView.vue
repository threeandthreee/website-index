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
          div.mb-4
            a(href="https://raceswild.3and3.dev")
              strong Races Wild
            span &nbsp;- Organizing and restreaming biweekly races.
          div.mb-4
            a(href="https://github.com/threeandthreee/Archipelago/releases")
              strong AP LADX
            span &nbsp;- I'm currently the maintainer of Link's Awakening: DX for the <a href="https://archipelago.gg">Archipelago</a> multi-game multi-world randomizer.
          div.mb-4
            a(href="https://vod-sync.3and3.dev")
              strong Vod Sync
            span &nbsp;- Sync YouTube or Twitch vods to a reference point and playback with shared controls. Designed with speedrunning in mind -- it's good for comparing full runs, comparing segments, and race playback. I may think of some other ideas with this in the future, but I feel ok calling this one done.
          div
            a(href="https://games.3and3.dev")
              strong Games
            span &nbsp;- Well, game. But I made an index so here it is.
      v-card-actions
        link-btn(url="https://github.com/threeandthreee" icon="github.svg" desc="Github")
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
              v-card(href="https://comics.3and3.dev" hover height="150px" outlined)
                div(style="height:120px")
                  comic-preview(width="100%" height="100%")
                .overline.text-center.mx-auto.py-auto Comics
    v-card.my-2(outlined :width="width")
      v-card-title Speedrunning
      v-card-text
        .d-flex.flex-column
          span I stream my runs on <a href="https://twitch.tv/threeandthree">twitch</a> after the kids are asleep. Vods are on <a href="https://www.youtube.com/playlist?list=PL_TLWBSKyqgP1Jo1fjYeq7Atwhdem3IdH">youtube</a>. I also participate in <a href="https://raceswild.3and3.dev">speedrun races</a> every other week with some friends.
          v-divider.my-2.d-none
          v-card.mt-3.mb-n3.py-2.pl-2(outlined)
            personal-bests
      v-card-actions
        link-btn(url="https://twitch.tv/threeandthree" icon="twitch.svg" desc="Twitch")
        link-btn(url="https://youtube.com/@threeandthree" icon="youtube.svg" desc="Youtube")
        link-btn(url="https://www.speedrun.com/user/threeandthree" icon="src.png" desc="Speedrun.com")
        link-btn(url="https://racetime.gg/user/DMLq1oZAge3OeQG8" icon="racetime.svg" desc="Racetime.gg")
    .d-flex.justify-content-center.mt-4
      v-icon mdi-email
      .body-1.mr-2 :
      .body-1 alex
      v-icon mdi-at
      .body-1 3and3.dev
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
