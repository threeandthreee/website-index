<template lang="pug">
v-tooltip(bottom)
  template(v-slot:activator="{ on, attrs }")
    v-btn.my-0.mx-1(icon :href="url" v-bind="attrs" v-on="on")
      v-img(:src="require(`../assets/${icon}`)" contain height=30 width=30)
  span {{desc}}
</template>

<script>
export default {
  props: ['url', 'icon', 'desc']
}
</script>