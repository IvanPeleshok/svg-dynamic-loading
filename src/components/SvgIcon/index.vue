<template>
  <component :is="dynamicIcon" />
</template>

<script>
export default {
  name: 'svg-icon',
  props: {
    name: {
      type: String,
      required: true
    }
  },
  computed: {
    dynamicIcon() {
      const name = this.name

      return () => import(`@/assets/${name}.svg`)
    }
  }
};
</script>
