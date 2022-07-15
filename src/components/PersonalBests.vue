<template lang="pug">
div
  .subtitle-2 Personal Bests
  .d-flex.flex-column(v-for="(runs, game) of processed")
    .overline.nowrap {{game}}
    .caption.ml-2(v-for="run of runs") &bull; {{run}}
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
        if(item.run.game in acc) {
          acc[item.run.game].push(item)
        } else {
          acc[item.run.game] = [item]
        }
        return acc
      }, {})
      let processed = Object.fromEntries(await Promise.all(Object.entries(gameGrouped).map(async ([gameId, items]) => {
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
          let time = item.run.times.primary.slice(2, -1).replace(/[HM]/g, ':')
          return `${category.name} ${subCategories.join(', ')} - ${time} (${ordinal(item.place)})`.replace(/\s+/g, ' ')
        }))
        return [game.names.international, times]
      })))
      this.processed = processed
    } catch {
      // do nothing
    }
  }
}
</script>