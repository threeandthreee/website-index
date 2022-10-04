<template lang="pug">
div.personal-bests
  .subtitle-2.top-title Personal Bests
  .d-flex.flex-column.game(v-for="([game, runs]) of processed")
    .overline.nowrap.title {{game}}
    .caption.entry(v-for="run of runs") &bull; {{run}}
</template>

<script>
import axios from 'axios'
import ordinal from 'ordinal'

const api = 'https://www.speedrun.com/api/v1'
const user = '8639p008'

export default {
  data: () => ({
    processed: {}
  }),
  async mounted() {
    try {
      let personalBestsResponse = await axios.get(`${api}/users/${user}/personal-bests`)
      let personalBests = personalBestsResponse.data.data
      let gameGrouped = personalBests.reduce((acc, item) => {
        let entry = acc.find(it => it[0] == item.run.game)
        if(entry)
          entry[1].push(item)
        else
          acc.push([item.run.game, [item]])
        return acc
      }, [])
      let processed = await Promise.all(gameGrouped.map(async ([gameId, items]) => {
        let gameResponse = await axios.get(`${api}/games/${gameId}`)
        let game = gameResponse.data.data
        let times = await Promise.all(items.map(async item => {
          let categoryResponse = await axios.get(`${api}/categories/${item.run.category}`)
          let category = categoryResponse.data.data
          let variablesResponse = await axios.get(`${api}/categories/${item.run.category}/variables`)
          let variables = variablesResponse.data.data
          let subCategories = variables.filter(it => it['is-subcategory']).map(it => {
            let val = item.run.values[it.id]
            return it.values.values[val].label
          })
          let time = item.run.times.primary.slice(2).toLowerCase().replace('h', 'h ').replace('m', 'm ')
          return `${category.name} ${subCategories.join(', ')}: ${time} (${ordinal(item.place)})`.replace(/\s+/g, ' ')
        }))
        return [game.names.international, times]
      }))
      this.processed = processed
    } catch {
      // do nothing
    }
  }
}
</script>

<style lang="stylus">
.personal-bests
  .top-title
    margin-top: -4px
    margin-bottom: -8px
  .game
    margin-top: 20px
    margin-bottom: 4px
    border-left: 1px solid #ccc
    padding: 0 0 0 8px
    .title
      margin-top: -12px
      margin-bottom: -12px
    .entry
      margin-top: 4px
      margin-bottom: -4px
      margin-left: 12px
      text-indent: -8px
</style>