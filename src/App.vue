<template lang="pug">
v-app
  v-main
    router-view
</template>

<script>
export default {
  name: 'App',

  data: () => ({
    //
  }),
};
</script>

<style lang="stylus">
.top-title
  font-weight: 900
  font-size: 3em
  text-align: center
.top-title-middle
  text-align: center
  font-weight: 100
  font-size: 2em
  margin-top: -16px
  margin-bottom: -16px
</style>