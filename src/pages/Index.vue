<template lang="pug">
  Layout
    h1 Your next protoframework
    p Ether is the missing part to kickstart any of your projects,<br> boosting your velocity and creativity.
    .mt-1
      g-link(class="button button--primary" to="/docs") See docs
</template>

<script>
export default {
  metaInfo: {
    title: 'The protoframework'
  }
}
</script>

<style lang="stylus" scoped>
.mt-1
  margin-top 1rem
</style>
