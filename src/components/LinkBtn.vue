<template lang="pug">
v-tooltip(bottom)
  template(v-slot:activator="{ on, attrs }")
    v-btn.ma-0(icon :href="url" v-bind="attrs" v-on="on")
      v-img(:src="require(`../assets/${icon}`)" contain height=20 width=20)
  span {{desc}}
</template>

<script>
export default {
  props: ['url', 'icon', 'desc']
}
</script>