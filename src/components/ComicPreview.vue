<template lang="pug">
iframe(src="https://3and3.the-comic.org/comics" :width="width" :height="height" scrolling="no" style="border:0;pointer-events:none;touch-action:none")
</template>

<script>
export default {
  props: ['width', 'height']
}
</script>