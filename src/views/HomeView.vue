<template lang="pug">
v-container
  .top-title WHAT I'VE DONE
  .top-title-middle and
  .top-title WHAT I'M DOING
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
      v-card-text Doodles go on the <strong>Tumblr</strong>. My earliest stuff is on <strong>DeviantArt</strong>. There was a middle period where I worked on comics for a now dead website, getting something up to display my old comics is on my to-do list.
      v-card-actions
        link-btn(url="https://blog.3and3.dev" icon="tumblr.svg" desc="Tumblr")
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
